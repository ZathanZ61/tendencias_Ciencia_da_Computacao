# Unidade IV — Aplicações e Limitações: Agentes de IA, Chatbots e Ética

**Disciplina:** Tendências em Ciência da Computação  
**Professora:** Kadidja Valéria  
**Estudante:** Nathan Ferreira dos Santos  
**Curso:** Ciência da Computação  
**Projeto:** Sistema de Triagem Automática de Chamados — desenvolvimento colaborativo com Douglas

## 1. Apresentação

A Unidade IV aborda a aplicação de agentes de Inteligência Artificial, chatbots e ferramentas de conversação, além das limitações técnicas, dos vieses algorítmicos e da responsabilidade social no uso da IA.

Para esta etapa, o grupo manteve o tema de triagem de chamados de suporte de TI iniciado como mini projeto na etapa anterior e trabalhou em uma versão ampliada: um sistema que recebe solicitações, utiliza IA como apoio à classificação inicial, registra informações e oferece um chatbot para consulta do andamento.

O desenvolvimento é colaborativo com Douglas. Esta pasta registra a participação acadêmica e a análise do projeto, mas **não substitui nem replica o repositório original da aplicação**.

## 2. Identificação e acesso ao projeto

- **Repositório original (código e desenvolvimento colaborativo):** [Sistema de Triagem Automática — Vibe Coder](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder)
- **Demonstração publicada:** [Abrir aplicação na Vercel](https://sistema-de-triagem-eosin.vercel.app/)
- **Repositório acadêmico desta disciplina:** [tendencias_Ciencia_da_Computacao](https://github.com/ZathanZ61/tendencias_Ciencia_da_Computacao)

O repositório de Douglas é a fonte do código do projeto. Atualizações de implementação e publicação da aplicação permanecem sob o fluxo de trabalho colaborativo já existente. Esta documentação não altera arquivos, configurações ou hospedagem desse repositório.

## 3. Objetivo da solução

**Objetivo geral:** demonstrar como IA generativa, automação e chatbot podem apoiar o recebimento, a organização e o acompanhamento de chamados de suporte de TI, mantendo a revisão humana como parte do processo.

**Objetivos específicos:**
- receber solicitações por meio de um formulário web;
- validar os dados e gerar um protocolo de atendimento;
- utilizar IA para sugerir categoria, prioridade, resumo e orientação inicial;
- registrar os dados do chamado em uma planilha;
- enviar mensagens de confirmação e alertas por e-mail;
- permitir consulta do andamento por meio de chatbot;
- analisar limitações, riscos, privacidade, vieses e responsabilidade humana.

## 4. Tecnologias identificadas na documentação do projeto

- **n8n Cloud:** automação e integração dos fluxos;
- **OpenAI e Gemini:** serviços de IA utilizados em etapas distintas;
- **Google Sheets:** armazenamento e consulta dos registros;
- **Gmail:** envio de confirmações e notificações;
- **HTML, CSS e JavaScript:** interface web;
- **Vercel:** hospedagem da interface publicada.

A presença de uma tecnologia na arquitetura não significa, por si só, que todas as integrações foram testadas nesta documentação. A validação de cada fluxo depende de execução no ambiente com as respectivas credenciais.

## 5. Organização das atividades da Unidade IV

| Data | Atividade prevista | Registro nesta pasta |
|---|---|---|
| 05/11 | Criação de agentes de IA | [01 — Agentes de IA](docs/01-agentes-de-ia.md) |
| 12/11 | Chatbot e ferramentas de chatbot | [02 — Especificação do chatbot](docs/02-chatbot-especificacao.md) |
| 19/11 | Viés algorítmico e responsabilidade social | [03 — Ética e responsabilidade](docs/03-vies-algoritmico-e-etica.md) |
| 26/11 | Projeto e apresentação da solução inteligente | [04 — Projeto aplicado](docs/04-projeto-solucao-inteligente.md) |
| 26/11 | Integração dos conceitos e repositório | [05 — Validação e limitações](docs/05-validacao-e-limitacoes.md) |

## 6. Como a solução funciona — visão geral

1. O solicitante preenche o formulário web com os dados do problema.
2. A aplicação valida as informações e gera um protocolo.
3. Um fluxo de automação encaminha os dados para análise assistida por IA.
4. A classificação sugerida é utilizada para organizar o registro do chamado.
5. Os dados são registrados no Google Sheets.
6. O Gmail é utilizado para confirmação ao solicitante e alerta de prioridade alta.
7. O chatbot, apoiado pelo Gemini, recebe protocolo e e-mail para consultar informações do chamado e pode registrar informações adicionais.

A IA oferece sugestões e apoio operacional. A classificação automática não deve ser tratada como decisão infalível nem substituir a avaliação de uma pessoa responsável.

## 7. Limitações e responsabilidade

A solução depende de serviços externos, disponibilidade de internet, credenciais e configuração correta das integrações. Modelos generativos podem produzir classificações incorretas, interpretações incompletas ou respostas inconsistentes. Dados pessoais e informações potencialmente sensíveis precisam de proteção, acesso restrito e finalidade definida.

A documentação dos testes deve refletir somente execuções comprovadas. Cenários ainda não executados permanecem identificados como pendentes, sem serem apresentados como aprovados.

## 8. Documentos

- [01 — Agentes de IA](docs/01-agentes-de-ia.md)
- [02 — Especificação do chatbot](docs/02-chatbot-especificacao.md)
- [03 — Viés algorítmico e responsabilidade social](docs/03-vies-algoritmico-e-etica.md)
- [04 — Projeto de solução inteligente](docs/04-projeto-solucao-inteligente.md)
- [05 — Validação, limitações e próximos passos](docs/05-validacao-e-limitacoes.md)

---

*Documentação acadêmica da Unidade IV. O código-fonte e a evolução da aplicação permanecem no repositório colaborativo indicado acima.*
