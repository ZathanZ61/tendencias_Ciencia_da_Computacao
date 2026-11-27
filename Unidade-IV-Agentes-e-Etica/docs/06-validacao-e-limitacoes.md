# 06 — Validação, limitações e próximos passos

## 1. Objetivo da validação

A validação deve verificar se a aplicação recebe dados corretamente, gera e registra protocolos, utiliza a IA de forma controlada, envia notificações e permite consultar chamados pelo chatbot.

Este documento diferencia funcionalidades descritas na arquitetura de testes efetivamente comprovados. Não se deve declarar aprovação sem evidência de execução.

## 2. Cenários de teste

| ID | Cenário | Resultado esperado | Situação documental |
|---|---|---|---|
| T01 | Enviar formulário com dados válidos | Gerar protocolo e iniciar o fluxo | Duas aberturas reais relatadas em 27/11/2026; ver T12 e T13 |
| T02 | Enviar formulário com campos obrigatórios vazios | Impedir envio ou informar campos ausentes | A comprovar em execução |
| T03 | Solicitação classificada como prioridade alta | Registrar a sugestão e disparar alerta conforme configuração | Classificação Rede/Internet / Alta em T13; Douglas confirmou ao responsável pelo registro que o alerta interno está funcionando. |
| T04 | IA indisponível | Tratar falha sem inventar classificação | A comprovar em execução |
| T05 | Consultar protocolo e e-mail correspondentes | Exibir dados do chamado localizado | Chatbot respondeu status Aberto em T13; demais consultas pendentes |
| T06 | Consultar protocolo inexistente | Informar que não encontrou o registro | A comprovar em execução |
| T07 | Informar e-mail diferente | Não revelar dados do chamado | A comprovar em execução |
| T08 | Consultar durante indisponibilidade do Gemini | Informar falha de forma controlada | A comprovar em execução |
| T09 | Enviar informação adicional pelo chatbot | Registrar a informação no destino configurado | A comprovar em execução |
| T10 | Solicitar dado não existente no registro | Não inventar resposta | A comprovar em execução |
| T11 | Verificar acesso a chamados de outros usuários | Impedir exposição indevida | A comprovar em execução |

### Testes reais relatados em 27/11/2026

Os protocolos exibidos nos e-mails de confirmação são `CH-20261126-P725` (Software/Média) e `CH-20261126-VCTH` (Rede/Internet/Alta).

| ID | Entrada / cenário | Resultado observado | Situação |
|---|---|---|---|
| T12 | Chamado sobre impossibilidade de realizar a saída de produtos no sistema de coleta | A página confirmou a abertura, gerou o protocolo `CH-20261126-P725`, classificou como Software / Média e exibiu resumo e sugestão inicial. | Executado pelo usuário; página e e-mail de confirmação recebidos. |
| T13 | Instabilidade ou queda de internet afetando todo o setor | A página confirmou a abertura; protocolo `CH-20261126-VCTH`; categoria Rede/Internet; prioridade Alta; sugestão inicial exibida. O chatbot respondeu que o status era Aberto. O usuário confirmou o recebimento do e-mail de confirmação. | Executado pelo usuário; página, chatbot e recebimento do e-mail confirmados por relato. |

**Confirmação posterior do mantenedor:** Nathan informou que Douglas confirmou o funcionamento da gravação no Google Sheets, do alerta interno de prioridade alta e dos workflows ativos no n8n. Esta documentação registra a confirmação do responsável pelo projeto, mas não representa uma inspeção independente realizada por esta revisão. A exportação e o versionamento dos workflows JSON continuam pendentes de comprovação no Git.

## 3. Evidências necessárias

Para marcar os cenários como aprovados, recomenda-se guardar:
- captura de tela do formulário preenchido com dados fictícios;
- protocolo gerado;
- registro correspondente na planilha;
- e-mail de confirmação ou alerta recebido;
- conversa de consulta no chatbot;
- resultado de entradas inválidas e de falhas simuladas;
- data da execução e versão do fluxo utilizado.

Não incluir senhas, tokens, chaves de API ou dados pessoais reais nas evidências públicas.

## 4. Limitações técnicas identificadas na análise documental

Os pontos abaixo são itens de atenção observados na documentação e na análise anterior do repositório. Devem ser reconferidos na versão que Douglas atualizar:

1. **Exportação dos fluxos:** a árvore consultada do repositório principal não contém exportações JSON dos workflows. Douglas confirmou o funcionamento dos fluxos na instância n8n, mas isso não comprova que os arquivos JSON estejam exportados e versionados no Git. É importante manter os exports sanitizados, sem credenciais ou segredos.
2. **Arquivo do chatbot:** o README antigo citava `n8n/chatbot-chamados-n8n.json`, mas esse arquivo não foi localizado no caminho informado na branch `main`. Isso não prova que o chatbot não esteja funcionando; significa que sua reprodução a partir do Git depende de obter a exportação atual.
3. **URLs e estado do n8n:** a documentação foi alinhada ao endereço de demonstração confirmado `https://sistema-de-triagem-automatica.vercel.app/`. Douglas confirmou que os workflows estão funcionando na instância n8n; a revisão registra essa confirmação, sem acesso direto ao painel.
4. **Testes incompletos:** duas execuções foram relatadas em 27/11/2026. A confirmação do mantenedor também cobre a gravação no Sheets e o alerta interno; os demais cenários da matriz permanecem pendentes.
5. **Atualização de status:** se o andamento for alterado manualmente na planilha, o chatbot depende da atualização do registro para apresentar a informação correta.
6. **Segurança dos webhooks:** endpoints públicos exigem validação de entradas, limitação de abuso e proteção contra chamadas indevidas.
7. **Dependência externa:** falhas no n8n, nos provedores de IA, no Google Sheets, no Gmail ou na hospedagem podem interromper partes do serviço.

## 5. Segurança e manutenção

- manter chaves e credenciais fora dos arquivos públicos;
- revisar permissões de acesso às planilhas e ferramentas;
- validar dados no servidor/fluxo, não apenas na interface;
- limitar dados pessoais enviados aos modelos;
- registrar erros sem armazenar segredos;
- revisar os endpoints sempre que houver atualização ou mudança de ambiente;
- exportar e versionar os fluxos do n8n sem informações sensíveis.

## 6. Próximos passos técnicos

Os próximos ajustes de implementação pertencem ao fluxo colaborativo no repositório original. Entre os itens que merecem conferência estão:
- obter e versionar, após sanitização, os exports JSON dos fluxos de abertura e chatbot;
- guardar evidência documental da confirmação de funcionamento feita pelo mantenedor (sem expor credenciais ou dados pessoais);
- executar os cenários pendentes com dados fictícios;
- registrar evidências sem dados pessoais, credenciais ou tokens;
- revisar proteção de webhooks e acesso aos registros;
- atualizar esta documentação quando houver evidências novas.

## 7. Conclusão

O projeto demonstra como IA generativa, automação e chatbot podem ser combinados para apoiar uma atividade real de suporte. Entretanto, a confiabilidade depende da integração correta dos serviços, da qualidade dos dados, dos testes e da supervisão humana.

A solução deve ser apresentada com transparência: funcionalidades descritas não equivalem automaticamente a funcionalidades validadas. A melhoria contínua exige registrar resultados reais, corrigir falhas e avaliar os impactos sobre os usuários.

**Fontes do projeto:** [repositório colaborativo](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder) · [aplicação testada](https://sistema-de-triagem-automatica.vercel.app/) · [casos de teste atualizados](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder/blob/docs/auditoria-testes-seguranca/docs/casos-de-teste.md)
