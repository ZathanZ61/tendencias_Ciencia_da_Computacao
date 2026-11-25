# 04 — Projeto de solução inteligente

## 1. Nome do projeto

**Sistema de Triagem Automática de Chamados de Suporte**

Projeto colaborativo desenvolvido por Nathan Ferreira dos Santos e Douglas, com foco na organização de solicitações de suporte de Tecnologia da Informação.

## 2. Problema

Solicitações de suporte podem chegar com descrições incompletas e sem padronização. Isso dificulta a identificação do tipo de problema, a organização dos registros e a definição de prioridade.

A proposta é utilizar uma interface web, automação e IA generativa para apoiar a abertura, a classificação inicial e o acompanhamento dos chamados.

## 3. Solução proposta

A aplicação reúne dois caminhos principais:

### Abertura e triagem
1. O usuário preenche o formulário web.
2. Os dados são validados e um protocolo é gerado.
3. O fluxo de automação utiliza IA para sugerir classificação, prioridade, resumo e orientação.
4. O chamado é registrado no Google Sheets.
5. O Gmail envia uma confirmação ao solicitante e pode emitir alerta para chamados de prioridade alta.

### Consulta pelo chatbot
1. O usuário acessa o chatbot.
2. Informa protocolo e e-mail.
3. O chatbot utiliza Gemini para interpretar a solicitação e consultar os dados disponíveis.
4. A resposta deve refletir o registro encontrado.
5. O fluxo pode registrar informações adicionais enviadas pelo usuário.

## 4. Arquitetura tecnológica

| Componente | Tecnologia | Responsabilidade |
|---|---|---|
| Interface web | HTML, CSS e JavaScript | Formulário e interação com o usuário |
| Automação | n8n Cloud | Orquestração dos fluxos e integrações |
| IA para triagem | OpenAI | Apoio à interpretação e classificação |
| Chatbot | Gemini | Conversação e consulta de chamados |
| Armazenamento | Google Sheets | Registro dos chamados |
| Notificações | Gmail | Confirmações e alertas |
| Hospedagem da interface | Vercel | Disponibilização da aplicação web |

A tabela descreve a arquitetura registrada no projeto. A execução de cada integração depende da configuração vigente dos serviços e das credenciais correspondentes.

## 5. Diagrama conceitual

```mermaid
flowchart TD
    U[Solicitante] --> WEB[Interface web]
    WEB --> N8N[Fluxo de abertura no n8n]
    N8N --> IA[OpenAI: sugestão de triagem]
    IA --> SHEETS[Google Sheets]
    N8N --> MAIL[Gmail: confirmação e alerta]
    U --> BOT[Chatbot]
    BOT --> GEM[Gemini]
    GEM --> SHEETS
    SHEETS --> BOT
    BOT --> U
```

## 6. Relação com os conteúdos da Unidade IV

- **Agentes de IA:** utilização de modelos para interpretar solicitações e apoiar o atendimento.
- **Chatbot:** interface conversacional para consulta de chamados.
- **Ferramentas de integração:** n8n conecta interface, modelos de IA, planilha e e-mail.
- **IA generativa:** modelos de linguagem produzem interpretações e respostas a partir do contexto recebido.
- **Limitações:** dependência de serviços externos, erros de interpretação e necessidade de dados atualizados.
- **Ética:** revisão humana, privacidade, prevenção de vieses e transparência.

## 7. Demonstração

- [Aplicação publicada na Vercel](https://sistema-de-triagem-eosin.vercel.app/)
- [Repositório original do projeto colaborativo](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder)

A demonstração é o endereço de publicação conhecido do projeto. A disponibilidade e o comportamento atual precisam ser conferidos no momento da apresentação.

## 8. Divisão de responsabilidades e autoria

O projeto é colaborativo. O repositório de Douglas contém a implementação original e é o local em que o desenvolvimento e as atualizações técnicas continuam. Esta documentação acadêmica organiza a apresentação da Unidade IV no repositório pessoal de Nathan e referencia o trabalho conjunto, sem reivindicar autoria exclusiva.

## 9. Roteiro curto para apresentação

1. Apresentar o problema: dificuldade de organizar e acompanhar chamados de TI.
2. Mostrar a interface de abertura e explicar a geração do protocolo.
3. Explicar como a IA sugere categoria, prioridade e resumo.
4. Mostrar como os dados são registrados e como ocorrem as notificações.
5. Demonstrar o chatbot e explicar a consulta por protocolo e e-mail.
6. Apresentar limitações: erros da IA, dependência de integrações e atualização dos registros.
7. Concluir destacando a supervisão humana, a privacidade e a responsabilidade no uso da IA.
