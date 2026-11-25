# 02 — Chatbot e especificação funcional

## 1. Objetivo

O chatbot foi pensado para permitir que o solicitante acompanhe um chamado sem precisar abrir uma nova solicitação ou entrar em contato diretamente com a equipe para cada consulta.

A solução utiliza Gemini como tecnologia conversacional e consulta os registros associados ao atendimento.

## 2. Identificação do usuário e consulta

**Dados solicitados:**
- número do protocolo;
- e-mail utilizado na abertura do chamado.

A combinação desses dados funciona como uma verificação básica para localizar o registro correto. Ela não deve ser considerada, isoladamente, um mecanismo completo de autenticação para acesso a informações sensíveis.

## 3. Requisitos funcionais

| Código | Requisito |
|---|---|
| RF01 | Receber a mensagem do usuário em linguagem natural. |
| RF02 | Solicitar protocolo e e-mail quando necessários para localizar o chamado. |
| RF03 | Consultar os dados disponíveis no registro correspondente. |
| RF04 | Informar o andamento com base no conteúdo efetivamente encontrado. |
| RF05 | Solicitar esclarecimentos quando os dados forem insuficientes. |
| RF06 | Permitir o registro de informações adicionais quando o fluxo estiver configurado para isso. |
| RF07 | Informar quando não localizar o protocolo ou quando ocorrer falha na consulta. |

## 4. Requisitos não funcionais

- **Clareza:** respostas objetivas, em linguagem acessível.
- **Rastreabilidade:** não apresentar informações sem correspondência com o registro consultado.
- **Privacidade:** limitar os dados exibidos ao necessário para a finalidade do atendimento.
- **Segurança:** evitar exposição de informações de outros solicitantes.
- **Disponibilidade:** tratar indisponibilidade do modelo ou da planilha sem simular sucesso.
- **Transparência:** deixar claro que o atendimento é automatizado e que a IA pode cometer erros.

## 5. Exemplos de interação esperada

**Consulta válida**

Usuário: “Quero consultar meu chamado.”  
Chatbot: “Informe o protocolo e o e-mail utilizado na abertura para localizar o registro.”

Após localizar o chamado, o chatbot deve apresentar somente o andamento que estiver registrado.

**Protocolo não localizado**

Chatbot: “Não encontrei um chamado com os dados informados. Confira o protocolo e o e-mail ou procure a equipe responsável.”

**Dados insuficientes**

Chatbot: “Preciso do protocolo e do e-mail cadastrado para tentar localizar o atendimento.”

**Falha na integração**

Chatbot: “Não foi possível consultar o registro neste momento. Tente novamente mais tarde ou entre em contato com a equipe.”

As mensagens são exemplos de comportamento esperado, não transcrições de testes reais.

## 6. Limitações

- A resposta depende da qualidade e da atualização dos dados registrados.
- O chatbot não deve presumir que um chamado foi resolvido apenas porque o usuário descreveu uma solução.
- Se o status for atualizado manualmente na planilha, a consulta refletirá o registro disponível no momento da leitura.
- Modelos generativos podem interpretar incorretamente perguntas ou produzir conteúdo não solicitado.
- Protocolo e e-mail podem não ser suficientes para proteger dados de maior sensibilidade; controles adicionais podem ser necessários conforme o tipo de informação armazenada.

## 7. Critérios de teste

1. Consultar protocolo e e-mail correspondentes.
2. Informar protocolo inexistente.
3. Informar e-mail diferente do cadastrado.
4. Enviar mensagem sem os dados necessários.
5. Solicitar informação que não existe no registro.
6. Simular indisponibilidade do Gemini.
7. Verificar se o chatbot evita revelar dados de outro chamado.
8. Enviar informação adicional e conferir se ela foi registrada corretamente.

Os cenários devem ser executados no ambiente real de integração antes de serem marcados como aprovados.

**Implementação original:** [repositório colaborativo no GitHub](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder)
