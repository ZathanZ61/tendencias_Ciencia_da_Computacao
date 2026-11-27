# Unidade IV — Aplicações e Limitações: Agentes de IA, Chatbots e Ética

**Disciplina:** Tendências em Ciência da Computação  
**Professora:** Kadidja Valéria  
**Estudante:** Nathan Ferreira dos Santos  
**Curso:** Ciência da Computação  
**Projeto:** Sistema de Triagem Automática de Chamados — desenvolvimento colaborativo com Douglas

## 1. Apresentação

A Unidade IV aborda a aplicação de agentes de Inteligência Artificial, chatbots e ferramentas de conversação, além das limitações técnicas, dos vieses algorítmicos e da responsabilidade social no uso da IA.

Para esta etapa, o grupo manteve o tema de triagem de chamados de suporte de TI iniciado como mini projeto na etapa anterior e trabalhou em uma versão ampliada: um sistema que recebe solicitações, utiliza IA como apoio à classificação inicial, registra informações e oferece um chatbot para consulta do andamento.

A documentação desta pasta cobre as quatro semanas da unidade e a reflexão da A1: agentes e chatbot, privacidade e segurança, viés e responsabilidade social, projeto aplicado, validação e aprendizados.

O desenvolvimento é colaborativo com Douglas. Esta pasta registra a participação acadêmica e a análise do projeto, mas **não substitui nem replica o repositório original da aplicação**.

## 2. Identificação e acesso ao projeto

- **Repositório original (código e desenvolvimento colaborativo):** [Sistema de Triagem Automática — Vibe Coder](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder)
- **Demonstração publicada:** [Abrir aplicação na Vercel](https://sistema-de-triagem-automatica.vercel.app/)
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
| 05/11 | Criação de agentes de IA e ferramentas de chatbot | [01 — Agentes de IA](docs/01-agentes-de-ia.md) e [02 — Especificação do chatbot](docs/02-chatbot-especificacao.md) |
| 12/11 | Privacidade e segurança: estudo de caso com dados sensíveis | [03 — Privacidade e segurança](docs/03-privacidade-e-seguranca.md) |
| 19/11 | Viés algorítmico e responsabilidade social | [04 — Ética e responsabilidade](docs/04-vies-algoritmico-e-etica.md) |
| 26/11 | Projeto e apresentação da solução inteligente | [05 — Projeto aplicado](docs/05-projeto-solucao-inteligente.md) |
| 26/11 | Validação, limitações e integração dos conceitos | [06 — Validação e limitações](docs/06-validacao-e-limitacoes.md) |
| 26/11 | Avaliação A1: reflexão sobre aprendizados | [07 — Reflexão sobre aprendizados](docs/07-reflexao-aprendizados-a1.md) |

## 6. Como a solução funciona — visão geral

1. O solicitante preenche o formulário web com os dados do problema.
2. A aplicação valida as informações e gera um protocolo.
3. Um fluxo de automação encaminha os dados para análise assistida por IA.
4. A classificação sugerida é utilizada para organizar o registro do chamado.
5. Os dados são registrados no Google Sheets.
6. O Gmail envia a confirmação ao solicitante e o fluxo prevê uma ramificação de alerta para chamados classificados como prioridade Alta.
7. No acompanhamento, o frontend envia protocolo, e-mail, mensagem e identificador de sessão ao webhook do chatbot. O fluxo n8n localiza o chamado no Google Sheets e confere o e-mail antes de encaminhar os dados daquele registro ao assistente Gemini. O chatbot pode registrar informações adicionais no campo previsto.

A IA oferece sugestões e apoio operacional. A classificação automática não deve ser tratada como decisão infalível nem substituir a avaliação de uma pessoa responsável.

## 7. Limitações e responsabilidade

A solução depende de serviços externos, disponibilidade de internet, credenciais e configuração correta das integrações. Modelos generativos podem produzir classificações incorretas, interpretações incompletas ou respostas inconsistentes. Dados pessoais e informações potencialmente sensíveis precisam de proteção, acesso restrito e finalidade definida.

A documentação dos testes deve refletir somente execuções comprovadas. Em 26/11/2026 foram relatadas duas execuções na aplicação publicada: uma abertura classificada como Software/Média; e outra sobre instabilidade de internet, classificada como Rede/Internet/Alta, com consulta de status Aberto pelo chatbot e recebimento do e-mail de confirmação. Após essas execuções, Douglas confirmou ao responsável pela documentação que a gravação no Google Sheets, o alerta interno de prioridade alta e os workflows no n8n estão funcionando. Essa confirmação foi repassada por Nathan e não equivale a uma inspeção independente desta revisão. A exportação e o versionamento dos workflows JSON ainda precisam ser comprovados no Git. Os demais cenários permanecem pendentes.

## 8. Documentos

- [01 — Agentes de IA](docs/01-agentes-de-ia.md)
- [02 — Especificação do chatbot](docs/02-chatbot-especificacao.md)
- [03 — Privacidade e segurança](docs/03-privacidade-e-seguranca.md)
- [04 — Viés algorítmico e responsabilidade social](docs/04-vies-algoritmico-e-etica.md)
- [05 — Projeto de solução inteligente](docs/05-projeto-solucao-inteligente.md)
- [06 — Validação, limitações e próximos passos](docs/06-validacao-e-limitacoes.md)
- [07 — Reflexão sobre os aprendizados (A1)](docs/07-reflexao-aprendizados-a1.md)

## 9. Estado da implementação e das evidências

A aplicação de referência está publicada em [sistema-de-triagem-automatica.vercel.app](https://sistema-de-triagem-automatica.vercel.app/). O repositório de Douglas permanece como fonte do código. A documentação complementar das duas execuções e da auditoria está registrada na [Pull Request #2](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder/pull/2), ainda sujeita à revisão do mantenedor.

**Resultados relatados em 26/11/2026:**
- Abertura de chamado sobre saída de produtos no sistema de coleta: Software / Média, confirmação na página e sugestão inicial.
- Abertura de chamado sobre instabilidade de internet no setor: Rede/Internet / Alta; chatbot respondeu status Aberto; e-mail de confirmação recebido.
- Douglas confirmou o funcionamento da gravação no Sheets, do alerta interno de prioridade alta e dos workflows no n8n. A exportação/versionamento dos JSON permanece pendente de comprovação no repositório.

A árvore consultada do repositório principal não contém exportações JSON dos workflows; em particular, o arquivo de chatbot citado em instruções antigas não foi localizado no caminho indicado. Isso não significa que o chatbot não exista ou não funcione: a execução relatada confirma o uso do chatbot, mas a reprodução do workflow a partir do Git ainda depende da exportação sanitizada.

---

*Documentação acadêmica da Unidade IV. O código-fonte e a evolução da aplicação permanecem no repositório colaborativo indicado acima.*
