# 05 — Validação, limitações e próximos passos

## 1. Objetivo da validação

A validação deve verificar se a aplicação recebe dados corretamente, gera e registra protocolos, utiliza a IA de forma controlada, envia notificações e permite consultar chamados pelo chatbot.

Este documento diferencia funcionalidades descritas na arquitetura de testes efetivamente comprovados. Não se deve declarar aprovação sem evidência de execução.

## 2. Cenários de teste

| ID | Cenário | Resultado esperado | Situação documental |
|---|---|---|---|
| T01 | Enviar formulário com dados válidos | Gerar protocolo e iniciar o fluxo | A comprovar em execução |
| T02 | Enviar formulário com campos obrigatórios vazios | Impedir envio ou informar campos ausentes | A comprovar em execução |
| T03 | Solicitação classificada como prioridade alta | Registrar a sugestão e disparar alerta conforme configuração | Há registro anterior de um cenário aprovado com dados simulados; revalidar na versão atual |
| T04 | IA indisponível | Tratar falha sem inventar classificação | A comprovar em execução |
| T05 | Consultar protocolo e e-mail correspondentes | Exibir dados do chamado localizado | A comprovar em execução |
| T06 | Consultar protocolo inexistente | Informar que não encontrou o registro | A comprovar em execução |
| T07 | Informar e-mail diferente | Não revelar dados do chamado | A comprovar em execução |
| T08 | Consultar durante indisponibilidade do Gemini | Informar falha de forma controlada | A comprovar em execução |
| T09 | Enviar informação adicional pelo chatbot | Registrar a informação no destino configurado | A comprovar em execução |
| T10 | Solicitar dado não existente no registro | Não inventar resposta | A comprovar em execução |
| T11 | Verificar acesso a chamados de outros usuários | Impedir exposição indevida | A comprovar em execução |

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

1. **Exportação dos fluxos:** a documentação indicava que o fluxo de abertura não estava exportado/versionado no GitHub. É importante manter os fluxos exportados em JSON, sem credenciais ou segredos.
2. **Arquivo do chatbot:** foi necessário confirmar se o arquivo JSON citado no README existe no caminho informado e se pode ser importado.
3. **URLs de webhook:** havia divergência entre endereços descritos na documentação e o endereço referenciado pela interface. Deve existir uma única configuração atual e documentada.
4. **Testes incompletos:** a documentação anterior registrava um cenário aprovado com dados simulados e outros cenários pendentes. A situação deve ser atualizada somente após novas execuções.
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
- exportar e versionar os fluxos de abertura e chatbot;
- padronizar e documentar as URLs utilizadas;
- executar os cenários de teste com dados fictícios;
- registrar evidências da execução;
- revisar proteção de webhooks e acesso aos registros;
- atualizar esta documentação quando houver evidências novas.

## 7. Conclusão

O projeto demonstra como IA generativa, automação e chatbot podem ser combinados para apoiar uma atividade real de suporte. Entretanto, a confiabilidade depende da integração correta dos serviços, da qualidade dos dados, dos testes e da supervisão humana.

A solução deve ser apresentada com transparência: funcionalidades descritas não equivalem automaticamente a funcionalidades validadas. A melhoria contínua exige registrar resultados reais, corrigir falhas e avaliar os impactos sobre os usuários.

**Fontes do projeto:** [repositório colaborativo](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder) · [aplicação publicada](https://sistema-de-triagem-eosin.vercel.app/)
