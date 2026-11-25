# 02 — Escolha e configuração da plataforma

## Critérios considerados

A escolha das ferramentas deve considerar:
- facilidade de montar e compreender os fluxos;
- integração com serviços externos;
- possibilidade de validar entradas e tratar erros;
- suporte à integração com modelos de IA;
- custo, limites de uso e segurança;
- facilidade de demonstrar e documentar o protótipo.

## Ferramentas utilizadas no protótipo documentado

| Ferramenta | Responsabilidade |
|---|---|
| n8n Cloud | Construção e execução visual das automações. |
| OpenAI | Classificação inicial assistida por IA na abertura do chamado. |
| Google Gemini | Conversa para acompanhamento do chamado. |
| Google Sheets | Armazenamento tabular dos registros. |
| Gmail | Notificações ao solicitante e à equipe. |
| HTML, CSS e JavaScript | Interface web, formulário e chat. |
| Vercel | Hospedagem da página. |
| GitHub | Versionamento e documentação. |

## Justificativa da escolha do n8n

O n8n foi utilizado como núcleo de automação porque permite organizar visualmente etapas, condições, integrações e tratamento de erros. Isso se adequa ao objetivo de demonstrar um processo que recebe dados, valida informações, consulta serviços de IA, grava registros e envia notificações.

O Google Sheets foi utilizado como armazenamento simples para o protótipo, e o Gmail como canal de notificação. A página própria possibilitou criar uma interface específica para abertura e acompanhamento.

## Classificação da abordagem

A solução é **híbrida**:
- possui características Low Code na orquestração visual com n8n;
- utiliza código tradicional na interface em HTML, CSS e JavaScript;
- integra serviços de IA, que podem apoiar o processo de Vibecode quando utilizados de forma iterativa para gerar e revisar partes da solução.

Não é adequado classificar o sistema inteiro como No Code, pois há código convencional na interface e nas integrações.

## Configuração e evidências

A documentação técnica do projeto registra uma página publicada na Vercel e workflows no n8n. O repositório do projeto contém instruções de configuração e um arquivo exportado do workflow do chatbot. O workflow de abertura de chamados não estava exportado no repositório no momento descrito pelo README.

- [Repositório do projeto e documentação técnica](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder)
- [Demonstração web registrada no projeto](https://sistema-de-triagem-eosin.vercel.app/)

Antes de apresentar ou reutilizar o protótipo, é necessário confirmar se os serviços e workflows continuam ativos. Não inclua credenciais, tokens ou dados reais nas evidências.

## Limitações da escolha

A solução depende de serviços externos, contas, credenciais, cotas e disponibilidade das plataformas. O uso de planilha como armazenamento é adequado para uma demonstração, mas pode não atender a requisitos de escala, controle de acesso e auditoria de um sistema de produção.
