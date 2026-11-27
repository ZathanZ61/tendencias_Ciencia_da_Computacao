# 03 — Integração e arquitetura

## Visão geral

Na Unidade III, a proposta foi construir um mini projeto para organizar a triagem inicial de chamados de suporte de TI. O fluxo conceitual recebe uma solicitação, organiza os dados e utiliza automação e IA como apoio à classificação.

## Fluxo conceitual inicial

1. O usuário informa os dados básicos da solicitação.
2. A aplicação ou formulário recebe as informações.
3. O fluxo de automação verifica os dados necessários.
4. A IA pode apoiar a interpretação e a classificação inicial do chamado.
5. As informações organizadas ficam disponíveis para análise e encaminhamento.

### Diagrama simplificado

~~~mermaid
flowchart TD
    A[Usuário] --> B[Registro da solicitação]
    B --> C[Validação das informações]
    C --> D{Dados suficientes?}
    D -->|Não| E[Solicitar correção]
    D -->|Sim| F[Fluxo de automação]
    F --> G[Análise assistida por IA]
    G --> H[Triagem inicial do chamado]
    H --> I[Encaminhamento para análise da equipe]
~~~

O diagrama representa a ideia e o escopo didático da etapa inicial. Não é uma exportação literal de um workflow nem deve ser interpretado como descrição de todas as funcionalidades da versão posterior.

## Exercício de aplicação híbrida (22/10)

O exercício de criação de aplicação híbrida foi montado com três camadas:

| Camada | Abordagem | O que foi feito |
|---|---|---|
| Interface | Código tradicional | Formulário web em HTML, CSS e JavaScript para receber os dados da solicitação |
| Orquestração | Low Code | Fluxo no n8n para validar os dados, acionar a IA e encaminhar o registro |
| Interpretação | IA | Chamada a modelo de linguagem para sugerir categoria, prioridade e resumo |

A divisão mostra o que cada abordagem resolve melhor: a interface exige controle fino de validação e mensagens, enquanto a orquestração se beneficia da montagem visual e da troca de serviços sem reescrever código.

**Limites do registro:** nesta etapa o exercício foi conduzido como montagem do fluxo e da interface, sem exportação versionada dos workflows nem captura de execução. O artefato verificável do projeto é a aplicação evoluída apresentada na Unidade IV; esta seção documenta a concepção do exercício, não um teste concluído.

## Papel das abordagens

- **Low Code:** permite montar visualmente etapas, conexões e condições.
- **No Code:** possibilita configurar determinadas operações sem escrever código específico.
- **Vibecode:** permite utilizar instruções em linguagem natural para apoiar a criação e o ajuste de componentes.
- **Código tradicional:** pode ser utilizado para personalizar a interface e comportamentos que exigem maior controle.

## Evolução na Unidade IV

Na etapa seguinte, o grupo manteve a temática e ampliou a arquitetura. A versão evoluída passou a documentar dois fluxos principais:

### Abertura de chamados
- formulário web;
- validação e geração de protocolo;
- classificação assistida por IA;
- registro em Google Sheets;
- confirmação por Gmail e alerta para prioridade alta.

### Acompanhamento
- chatbot com Gemini;
- consulta por protocolo e e-mail;
- recuperação das informações do chamado;
- registro de informações adicionais enviadas pelo solicitante.

Essas funcionalidades pertencem à versão ampliada da Unidade IV. A separação permite demonstrar a evolução do projeto sem confundir as entregas das duas etapas.

## Limites e cuidados

- A IA deve apoiar a triagem, não substituir a avaliação humana.
- As informações precisam ser validadas antes do processamento.
- Falhas em serviços externos devem ser tratadas.
- Dados pessoais e credenciais precisam de proteção.
- A arquitetura conceitual não substitui testes dos fluxos efetivamente configurados.
