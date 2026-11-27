# 03 — Privacidade e segurança: estudo de caso com dados sensíveis

**Disciplina:** Tendências em Ciência da Computação
**Semana do plano de aulas:** 12/11 — Privacidade e segurança: estudo de caso sobre dados sensíveis
**Integrante:** Nathan Ferreira dos Santos
**Projeto:** Sistema de Triagem Automática de Chamados — trabalho conjunto com Douglas

## 1. Escopo deste documento

Este documento analisa como dados pessoais circulam no sistema de triagem e o que precisa ser controlado em cada etapa. Ele é uma análise acadêmica: não altera o código, as configurações ou a hospedagem da aplicação, que permanecem no [repositório colaborativo](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder) sob o fluxo de trabalho do projeto.

O sistema recebe nome, e-mail, setor e descrição do problema. A descrição é texto livre, portanto pode conter qualquer informação que o solicitante decidir colar ali — inclusive dados que não deveriam ser registrados.

## 2. Estudo de caso

> Cenário fictício, construído para esta atividade. Não corresponde a um chamado real nem a pessoa identificável.

Um colaborador abre um chamado com o seguinte texto:

```text
Socorro, o sistema de coleta não abre de jeito nenhum.
Segue o print da tela. Login: joao.silva
Senha: 123456
Meu CPF é 000.000.000-00 e meu telefone é (00) 90000-0000.
Preciso disso resolvido hoje.
```

O chamado é válido do ponto de vista operacional — há um problema real a resolver. Do ponto de vista de privacidade, ele carrega três tipos de dado que o fluxo não precisa para triar: credencial de acesso, CPF e telefone.

### 2.1 O que acontece com esse texto

1. O texto é enviado do navegador ao webhook do n8n.
2. A descrição completa é enviada no prompt ao modelo de triagem (OpenAI).
3. A descrição é gravada na planilha do Google Sheets.
4. Parte do conteúdo pode aparecer em notificações por e-mail.
5. O histórico de execução do n8n pode reter o payload.
6. Se o solicitante repetir o texto no chatbot, ele volta a circular, agora no fluxo do Gemini.

Em nenhuma dessas etapas a senha é útil para o atendimento. Ela apenas amplia a superfície de exposição.

## 3. Onde os dados circulam

| Etapa | Dados expostos | Risco principal | Controle esperado |
|---|---|---|---|
| Formulário no navegador (Vercel) | Todos os campos digitados | Conteúdo sensível colado em campo livre | Aviso no formulário e limite de caracteres |
| Webhook do n8n | Payload completo | Endpoint público sem autenticação de origem | Validação de entrada e limite de requisições |
| Prompt para o modelo de triagem | Descrição do chamado | Dado pessoal enviado a terceiro sem necessidade | Minimização e remoção de trechos sensíveis antes do envio |
| Google Sheets | Registro completo | Planilha compartilhada com mais gente que o necessário | Acesso restrito por pessoa e por função |
| Gmail | Trechos do chamado | Notificação enviada a destinatário incorreto | Conferência do endereço e conteúdo mínimo |
| Chatbot (Gemini) | Protocolo, e-mail e mensagem | Consulta indevida a chamado de terceiro | Verificação de e-mail, limite de tentativas e registro de acesso |
| Logs e histórico de execução | Payload e respostas | Retenção por tempo indefinido | Prazo de retenção e descarte definidos |

## 4. Riscos identificados

| Risco | Impacto | Mitigação proposta |
|---|---|---|
| Credencial enviada no texto do chamado | Vazamento de acesso a outro sistema | Orientar o usuário, mascarar padrões óbvios e excluir o trecho antes de registrar |
| CPF e telefone sem necessidade | Exposição de dado pessoal | Coletar apenas o necessário e não replicar em notificações |
| Protocolo previsível (`CH-AAAAMMDD-XXXX`) | Tentativa de adivinhar chamados alheios | Limite de tentativas por sessão e por IP |
| E-mail como única verificação | Acesso a dados por quem conhece protocolo e e-mail | Controle adicional para chamados com dado sensível |
| Planilha compartilhada amplamente | Acesso além da finalidade | Permissão individual e revisão periódica |
| Retenção indefinida em logs | Acúmulo desnecessário de dados | Prazo definido e rotina de descarte |
| Modelo de IA recebendo texto integral | Tratamento por terceiro sem base clara | Minimização e informação ao usuário |

## 5. Princípios da LGPD aplicados ao fluxo

A Lei nº 13.709/2018 (LGPD) orienta o tratamento de dados pessoais. Aplicada ao projeto:

| Princípio | O que significa aqui |
|---|---|
| Finalidade | O dado existe para triar e acompanhar o chamado, não para outros usos |
| Adequação | A descrição do problema é compatível com a finalidade; CPF e senha não são |
| Necessidade (minimização) | Coletar e repassar apenas o que a triagem exige |
| Segurança | Restringir acesso, proteger credenciais e evitar exposição em logs |
| Transparência | Informar que a descrição é processada por IA e armazenada em planilha |
| Prevenção | Tratar o vazamento como risco provável, não como exceção |
| Responsabilização | A equipe responde pelo que faz com os dados, inclusive os gerados por IA |

## 6. Checklist para o fluxo colaborativo

Itens a conferir no repositório da aplicação, com o responsável pelo desenvolvimento:

- [ ] aviso no formulário sobre o que não deve ser enviado (senhas, dados de cartão, documentos);
- [ ] validação de tamanho e de conteúdo no servidor, não apenas no navegador;
- [ ] remoção ou mascaramento de trechos sensíveis antes de enviar o texto ao modelo;
- [ ] limite de requisições no webhook e no chatbot;
- [ ] permissões da planilha revisadas por pessoa;
- [ ] prazo de retenção definido para logs e histórico de execução;
- [ ] mensagem clara ao usuário sobre uso de IA e armazenamento;
- [ ] canal para solicitar correção ou exclusão de dados.

## 7. O que este documento não comprova

- Não houve teste de intrusão nem auditoria de configuração da instância do n8n.
- Não há evidência, nesta documentação, de que os itens do checklist estejam implementados; eles são critérios de verificação.
- A verificação de e-mail no chatbot reduz acesso indevido, mas não é autenticação forte.
- A análise cobre o fluxo documentado; mudanças no repositório colaborativo podem alterar o cenário.

## 8. Referências

- [Lei nº 13.709/2018 — Lei Geral de Proteção de Dados Pessoais](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm)
- [ANPD — Autoridade Nacional de Proteção de Dados](https://www.gov.br/anpd/pt-br)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [NIST — AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
