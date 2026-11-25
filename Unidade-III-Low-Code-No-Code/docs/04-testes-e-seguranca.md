# 04 — Testes, validação e segurança

## Objetivo dos testes

Verificar se o protótipo recebe dados corretamente, trata entradas inválidas, registra chamados, lida com falhas da IA e protege as informações durante o acompanhamento.

## Validações descritas na documentação do projeto

### Abertura de chamado

| Campo | Regra documentada |
|---|---|
| Nome | Obrigatório; mínimo de 3 caracteres. |
| E-mail | Obrigatório; formato válido; normalizado para minúsculas. |
| Setor | Obrigatório; opções previstas: Financeiro, RH, Comercial, Operações ou Outro. |
| Descrição | Obrigatória; mínimo de 20 caracteres após remover espaços das extremidades. |

### Acompanhamento

| Campo | Regra documentada |
|---|---|
| Protocolo | Obrigatório; formato CH-AAAAMMDD-XXXX. |
| E-mail | Obrigatório; deve corresponder ao e-mail registrado no chamado. |
| Mensagem | Obrigatória; limite documentado de 1.000 caracteres. |

A validação no navegador melhora a experiência, mas não é suficiente: o workflow também deve validar os dados recebidos.

## Cenários de teste

A tabela diferencia o resultado esperado do estado de execução registrado. Não transforme um resultado esperado em aprovação sem executar o teste.

| Cenário | Resultado esperado | Estado encontrado no registro consultado |
|---|---|---|
| Chamado com prioridade alta e dados simulados | Registrar o chamado e gerar alerta à equipe. | Registrado como aprovado no material do projeto. |
| Dados obrigatórios ausentes ou inválidos | Rejeitar a entrada e informar erro. | Pendente no registro consultado. |
| Falha na classificação por IA | Utilizar o fallback documentado e manter o tratamento controlado. | Pendente no registro consultado. |
| Protocolo e e-mail corretos no chat | Consultar somente o chamado correspondente. | Pendente no registro consultado. |
| Protocolo correto com e-mail diferente | Recusar a consulta sem revelar os dados. | Pendente no registro consultado. |
| Mensagem nova do solicitante | Acrescentar informação ao registro para a equipe. | Pendente no registro consultado. |
| Tentativa de pedir dados de outros chamados | Recusar a solicitação. | Pendente no registro consultado. |
| Indisponibilidade do Gemini | Informar indisponibilidade sem alterar o chamado. | Pendente no registro consultado. |

**Limitação do registro:** o README do projeto informa que, no material de desenvolvimento consultado, apenas o cenário de prioridade alta estava marcado como aprovado com dados simulados; os demais ainda estavam pendentes naquele registro. Isso não confirma o estado atual da aplicação.

## Cuidados de segurança e privacidade

1. **Validação no servidor:** não confiar somente nas verificações feitas pela página.
2. **Proteção dos webhooks:** URLs públicas não são senhas. Implementar controles contra abuso, spam e requisições indevidas.
3. **Credenciais:** armazenar chaves e tokens no gerenciador de credenciais da plataforma, nunca no HTML, JavaScript ou README.
4. **Controle de acesso:** limitar o acesso à planilha às pessoas autorizadas.
5. **Dados pessoais:** usar dados fictícios nas demonstrações e evitar coletar informações desnecessárias.
6. **Verificação de identidade:** exigir protocolo e e-mail correspondente antes de apresentar informações do chamado.
7. **Revisão humana:** não permitir que a classificação da IA substitua a avaliação da equipe em incidentes críticos.
8. **Falhas de integração:** testar indisponibilidade de IA, planilha e e-mail e evitar apresentar uma operação como concluída quando o registro falhou.
9. **Prompt injection:** limitar os dados encaminhados ao modelo e manter as operações sensíveis sob controle do workflow, não da resposta livre da IA.

## Conclusão

Testar uma aplicação com IA não significa apenas verificar se ela responde em um cenário ideal. É necessário testar entradas inválidas, falhas externas, tentativas de acesso indevido e resultados incorretos. A documentação recuperada permite identificar esses cuidados, mas a aprovação integral depende de novas execuções e evidências.
