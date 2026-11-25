# 02 — Escolha e configuração da plataforma

## Critérios considerados

A escolha da plataforma para o mini projeto considerou:
- facilidade para estruturar visualmente as etapas;
- possibilidade de integrar serviços;
- suporte a condições e validação de dados;
- possibilidade de utilizar recursos de Inteligência Artificial;
- facilidade de testar e demonstrar o protótipo;
- custos, limites de uso e segurança.

## Plataforma de automação

O **n8n** foi utilizado como ferramenta de automação visual. Sua interface permite organizar etapas, conectar serviços e configurar condições sem precisar programar toda a lógica de integração manualmente.

A escolha está alinhada ao objetivo da Unidade III: compreender, na prática, como uma plataforma Low Code pode apoiar a construção de uma solução.

## Abordagem híbrida

O projeto se relaciona a três abordagens:

| Abordagem | Aplicação no contexto do projeto |
|---|---|
| Low Code | Organização visual das etapas e integrações por meio do n8n. |
| No Code | Uso de recursos configuráveis sem escrever código para cada operação. |
| Vibecode | Apoio de IA por meio de instruções em linguagem natural para criar, ajustar ou revisar partes da solução. |

A solução deve ser entendida como híbrida. A presença de uma interface construída com tecnologias web e de configurações específicas impede classificá-la integralmente como No Code.

## Ferramentas na evolução

Na versão ampliada da Unidade IV, a solução passou a documentar a integração de n8n, serviços de IA (OpenAI e Gemini), Google Sheets, Gmail, interface em HTML/CSS/JavaScript e publicação na Vercel.

Essa relação descreve a versão evoluída. Não significa que todas essas integrações e funcionalidades já faziam parte do escopo inicial da Unidade III.

## Justificativa

O n8n foi adequado ao objetivo acadêmico por tornar o fluxo de automação visual e facilitar a conexão entre diferentes serviços. O uso de IA permite experimentar classificação e interpretação de informações, mas os resultados precisam ser revisados e testados.

## Cuidados de configuração

- Não inserir senhas, tokens ou chaves de API em arquivos públicos.
- Utilizar credenciais armazenadas de forma segura na plataforma.
- Testar os fluxos com dados fictícios.
- Verificar entradas e respostas antes de considerar uma etapa concluída.
- Confirmar a disponibilidade dos serviços antes de uma demonstração.
