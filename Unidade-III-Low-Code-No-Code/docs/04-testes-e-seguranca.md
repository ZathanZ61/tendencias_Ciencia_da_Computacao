# 04 — Testes, validação e segurança

## Objetivo

Os testes da atividade devem verificar se o fluxo de triagem recebe informações adequadas, identifica entradas inválidas e apresenta um resultado coerente para análise inicial.

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

## Testes desta etapa

A verificação se limita aos cenários descritos acima. Validações de protocolo, fallback da classificação por IA e tratamento de indisponibilidade do modelo não fazem parte desta entrega.

## Conclusão

A validação é parte essencial do desenvolvimento Low Code e do uso de IA. Um fluxo funcionar em uma demonstração não significa que todos os casos estejam cobertos. É necessário registrar os cenários executados, seus resultados e as correções realizadas.
