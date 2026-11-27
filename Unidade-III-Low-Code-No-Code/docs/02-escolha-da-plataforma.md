# 02 — Escolha e configuração da plataforma

## Critérios considerados

A escolha da plataforma para a atividade considerou:
- facilidade para estruturar visualmente as etapas;
- possibilidade de integrar serviços;
- suporte a condições e validação de dados;
- possibilidade de utilizar recursos de Inteligência Artificial;
- facilidade de testar e demonstrar o protótipo;
- custos, limites de uso e segurança.

## Plataforma de automação

O **n8n** foi utilizado como ferramenta de automação visual. Sua interface permite organizar etapas, conectar serviços e configurar condições sem precisar programar toda a lógica de integração manualmente.

A escolha está alinhada ao objetivo da Unidade III: compreender, na prática, como uma plataforma Low Code pode apoiar a construção de uma solução.

## Comparação das plataformas avaliadas (08/10)

O quadro abaixo registra a comparação entre plataformas Low Code/No Code feita durante a escolha da ferramenta para o desafio de triagem. É um registro de avaliação, não um teste completo de cada plataforma.

| Critério | n8n | Make | Bubble |
|---|---|---|---|
| Tipo de ferramenta | Automação de fluxos | Automação de fluxos | Construção de aplicativos web |
| Forma de modelagem | Nós conectados, com condições e código opcional | Cenários visuais com módulos | Editor visual de telas, banco e lógica |
| Uso de IA | Nós de modelo de linguagem e agentes | Módulos de IA e chamadas HTTP | Chamadas a APIs de IA, com mais montagem manual |
| Integrações | Grande catálogo, incluindo Google Sheets e Gmail | Grande catálogo de serviços populares | Integrações via API e plugins |
| Curva de aprendizado | Média; exige entender fluxo e credenciais | Baixa para fluxos simples | Média; exige modelar telas e banco |
| Custos e limites | Instância própria ou nuvem, com limite de execuções | Plano gratuito limitado por operações | Plano gratuito limitado por aplicação |
| Aderência ao desafio | Alta: o problema é orquestrar etapas e integrações | Alta: mesma lógica de orquestração | Média: exigiria reconstruir a interface e o banco |

O n8n foi escolhido porque o núcleo do problema é a orquestração de etapas — validação, classificação por IA, registro e notificação — e não a construção de telas. O Bubble foi considerado adequado para aplicativos com banco e interface próprios, cenário diferente desta atividade.

## Abordagem híbrida

O projeto se relaciona a três abordagens:

| Abordagem | Aplicação no contexto do projeto |
|---|---|
| Low Code | Organização visual das etapas e integrações por meio do n8n. |
| No Code | Uso de recursos configuráveis sem escrever código para cada operação. |
| Vibecode | Apoio de IA por meio de instruções em linguagem natural para criar, ajustar ou revisar partes da solução. |

A solução deve ser entendida como híbrida. A presença de uma interface construída com tecnologias web e de configurações específicas impede classificá-la integralmente como No Code.

## Ferramentas desta etapa

A proposta desta etapa usa o n8n como orquestrador, um serviço de IA para a classificação inicial e uma planilha como registro. Interface própria, notificações e integrações adicionais não fazem parte desta entrega.

## Justificativa

O n8n foi adequado ao objetivo acadêmico por tornar o fluxo de automação visual e facilitar a conexão entre diferentes serviços. O uso de IA permite experimentar classificação e interpretação de informações, mas os resultados precisam ser revisados e testados.

## Cuidados de configuração

- Não inserir senhas, tokens ou chaves de API em arquivos públicos.
- Utilizar credenciais armazenadas de forma segura na plataforma.
- Testar os fluxos com dados fictícios.
- Verificar entradas e respostas antes de considerar uma etapa concluída.
- Confirmar a disponibilidade dos serviços antes de uma demonstração.
