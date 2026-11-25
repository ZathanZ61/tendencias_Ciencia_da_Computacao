# 04 — Testes, validação e segurança

## Objetivo

Os testes do mini projeto devem verificar se o fluxo de triagem recebe informações adequadas, identifica entradas inválidas e apresenta um resultado coerente para análise inicial.

## Cenários recomendados para o protótipo inicial

| Cenário | Resultado esperado |
|---|---|
| Solicitação com todos os dados necessários | O registro é recebido e segue para a triagem. |
| Campo obrigatório ausente | A entrada é sinalizada para correção. |
| Descrição pouco clara | A solicitação é identificada como necessitando de mais informações. |
| Classificação sugerida pela IA | A sugestão é apresentada para revisão humana. |
| Serviço de IA indisponível | O fluxo trata a falha sem apresentar uma classificação como concluída. |
| Dados com conteúdo inadequado ou inesperado | A entrada é validada e tratada de forma controlada. |

**Importante:** os cenários acima são critérios de validação recomendados. Não representam, por si só, testes executados ou aprovados.

## Cuidados de segurança

1. **Validação de dados:** conferir as informações recebidas antes de processá-las.
2. **Revisão humana:** tratar a classificação da IA como sugestão, especialmente em situações urgentes.
3. **Credenciais:** não publicar chaves de API, senhas ou tokens no código ou no GitHub.
4. **Privacidade:** utilizar dados fictícios nas demonstrações acadêmicas.
5. **Integrações:** prever falhas e evitar informar que uma operação foi concluída quando houver erro.
6. **Acesso:** limitar o acesso às ferramentas e aos registros às pessoas autorizadas.

## Testes na evolução da Unidade IV

A documentação da versão ampliada descreve validações mais específicas para a abertura de chamados e para o chatbot, incluindo conferência de protocolo e e-mail, fallback da classificação por IA e tratamento de indisponibilidade do Gemini.

No material técnico consultado para a versão evoluída, apenas o cenário de prioridade alta com dados simulados estava registrado como aprovado; os demais cenários constavam como pendentes naquele registro. Isso não comprova o estado atual dos testes.

## Conclusão

A validação é parte essencial do desenvolvimento Low Code e do uso de IA. Um fluxo funcionar em uma demonstração não significa que todos os casos estejam cobertos. É necessário registrar os cenários executados, seus resultados e as correções realizadas.
