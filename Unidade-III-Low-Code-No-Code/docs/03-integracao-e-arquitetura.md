# 03 — Integração e arquitetura

## Visão geral

O protótipo organiza o atendimento em dois fluxos principais: abertura de chamado e acompanhamento pelo chat.

## Fluxo A — Abertura do chamado

1. O solicitante preenche nome, e-mail, setor e descrição na página web.
2. A interface realiza verificações iniciais dos campos.
3. Os dados são enviados em JSON para um webhook do n8n.
4. O workflow valida e normaliza os dados e gera um protocolo.
5. Um modelo de IA sugere categoria, prioridade, resumo e orientação inicial.
6. Se a classificação falhar ou não puder ser utilizada, o fluxo documentado prevê valores alternativos (fallback).
7. O chamado é registrado no Google Sheets com status inicial.
8. O Gmail envia uma confirmação; chamados classificados com prioridade alta também podem gerar alerta à equipe.
9. O n8n retorna uma resposta para a página exibir a confirmação e o protocolo.

### Diagrama simplificado

~~~mermaid
flowchart TD
    A[Solicitante] --> B[Formulário web]
    B --> C[Webhook n8n]
    C --> D{Dados válidos?}
    D -->|Não| E[Retorno de erro]
    D -->|Sim| F[Normalização e protocolo]
    F --> G[Classificação assistida por IA]
    G --> H{Resposta utilizável?}
    H -->|Sim| I[Categoria e prioridade sugeridas]
    H -->|Não| J[Fallback]
    I --> K[Google Sheets]
    J --> K
    K --> L[Confirmação Gmail]
    K --> M{Prioridade alta?}
    M -->|Sim| N[Alerta à equipe]
    M -->|Não| O[Resposta à página]
    N --> O
~~~

## Fluxo B — Acompanhamento do chamado

1. O solicitante informa o protocolo e o e-mail utilizado na abertura.
2. O workflow procura o registro correspondente no Google Sheets.
3. O acesso às informações depende da correspondência entre protocolo e e-mail.
4. O Gemini recebe os dados do chamado já localizado e responde em linguagem natural.
5. Quando o solicitante envia uma informação nova, o workflow pode acrescentá-la ao registro para avaliação da equipe.

### Diagrama simplificado

~~~mermaid
flowchart TD
    A[Solicitante] --> B[Chat na página]
    B --> C[Webhook n8n]
    C --> D[Validar protocolo e e-mail]
    D --> E{Chamado localizado e conferido?}
    E -->|Não| F[Recusar consulta]
    E -->|Sim| G[Buscar dados do chamado]
    G --> H[Gemini responde]
    H --> I[Resposta ao solicitante]
    H --> J{Informação nova?}
    J -->|Sim| K[Registrar informação para equipe]
    J -->|Não| I
    K --> I
~~~

## Papel de cada abordagem

- **No Code / Low Code:** o n8n permite montar visualmente etapas, conexões, condições e integrações. A quantidade de código necessária depende da personalização de cada nó.
- **Vibecode:** o uso iterativo de IA pode apoiar a elaboração e o ajuste da interface, de trechos de lógica e de configurações. O resultado precisa ser revisado e testado.
- **Código tradicional:** HTML, CSS e JavaScript implementam a página, o formulário e o chat.

A solução é híbrida. Não é correto afirmar que tudo foi desenvolvido sem código ou exclusivamente por IA.

## Limites conhecidos

- A equipe atualiza manualmente informações como status, responsável e última atualização.
- O protótipo não documenta implementação de login completo, SLA ou atribuição automática de técnicos.
- A IA oferece apoio à triagem, mas não substitui a decisão da equipe de TI.
- Os webhooks precisam de proteção adicional antes de qualquer uso com dados reais.

## Referência técnica

A arquitetura foi reconstruída a partir do README e dos documentos descritos no repositório [Sistema de Triagem Automática — Vibe Coder](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder). Os diagramas acima são uma representação didática simplificada, não uma exportação literal dos workflows.
