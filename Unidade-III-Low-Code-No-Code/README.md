# Unidade III — Low Code, No Code e Vibecode

**Disciplina:** Tendências em Ciência da Computação  
**Professora:** Kadidja Valéria  
**Estudante:** Nathan Ferreira dos Santos  
**Curso:** Ciência da Computação

## 1. Apresentação da unidade

Esta unidade aborda o desenvolvimento de soluções digitais com plataformas visuais, ferramentas de automação e apoio de Inteligência Artificial. O objetivo é compreender como abordagens **Low Code**, **No Code** e **Vibecode** podem acelerar a construção de protótipos, sem dispensar planejamento, validação, segurança e revisão humana.

A documentação foi organizada a partir das orientações da professora e da recuperação do projeto em grupo que serviu de base para a etapa posterior: **Triagem Inteligente de Chamados de Suporte de TI**. O projeto está documentado no repositório de seu integrante/colaborador Douglas: [Sistema de Triagem Automática — Vibe Coder](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder).

> **Nota sobre a reconstrução:** os exercícios originais da Unidade III não estão mais disponíveis para o estudante. Este registro recompõe o processo com base no roteiro fornecido pela professora e na documentação técnica disponível do protótipo. Não representa a recuperação de arquivos originais nem atribui ao estudante, individualmente, todo o desenvolvimento do grupo.

## 2. Objetivo

Desenvolver e documentar um protótipo funcional que demonstre como ferramentas Low Code / No Code e recursos de IA podem automatizar uma etapa de um processo real, avaliando vantagens, limitações e cuidados de segurança.

## 3. Desafio escolhido

### Triagem inteligente de chamados de suporte de TI

O problema escolhido foi a dificuldade de organizar solicitações de suporte técnico que chegam por canais diferentes. Sem um registro centralizado, chamados podem se perder, a priorização pode ser inconsistente e o solicitante pode ter dificuldade para acompanhar o atendimento.

**Objetivo da solução:** permitir que uma pessoa registre um chamado em uma página web, receba um protocolo, tenha uma classificação inicial sugerida por IA e possa consultar o andamento por um assistente de chat.

**Público envolvido:**
- Solicitantes, que registram problemas e acompanham seus protocolos.
- Equipe de TI, que recebe chamados organizados e atualiza o andamento.

**Escopo documentado do protótipo:**
- Formulário web para abertura de chamados.
- Validação dos dados e geração de protocolo.
- Sugestão de categoria, prioridade, resumo e orientação inicial com IA.
- Registro das informações em Google Sheets.
- Confirmação por Gmail e alerta para chamados de prioridade alta.
- Chat de acompanhamento com Gemini, consultando protocolo e e-mail.

## 4. Plataforma e tecnologias escolhidas

| Ferramenta | Utilização |
|---|---|
| **n8n** | Orquestração visual dos fluxos, regras, validações, condições e integrações. |
| **OpenAI** | Apoio à classificação inicial dos chamados. |
| **Google Gemini** | Assistente conversacional para acompanhamento dos chamados. |
| **Google Sheets** | Registro centralizado dos chamados e informações de acompanhamento. |
| **Gmail** | Envio de confirmação e alertas. |
| **HTML, CSS e JavaScript** | Construção da página web e do chat integrado. |
| **Vercel** | Publicação da interface web. |
| **GitHub** | Versionamento e documentação do projeto. |

### Justificativa

O n8n foi adequado porque permite visualizar e organizar fluxos de automação, conectar serviços e criar condições para diferentes situações. O Google Sheets serviu como armazenamento simples para o protótipo, enquanto os serviços de IA apoiaram a classificação e a interação em linguagem natural.

A interface própria em HTML, CSS e JavaScript permitiu controlar a experiência do usuário. A Vercel facilitou a publicação da página. Essa composição demonstrou uma abordagem híbrida: automação visual combinada com código tradicional e assistência de IA.

## 5. Integração com Vibecode e Inteligência Artificial

O projeto combina automação visual e desenvolvimento de interface com recursos de IA.

Na abertura de chamados, o fluxo recebe os dados, valida as informações, gera um protocolo e encaminha a descrição para classificação assistida por IA. A resposta esperada contém categoria, prioridade, resumo e sugestão inicial. Há um caminho alternativo (fallback) para que uma falha ou resposta inválida da IA não impeça, por si só, a continuidade prevista do fluxo.

No acompanhamento, o Gemini responde a perguntas sobre um chamado localizado previamente. A busca e a conferência do protocolo com o e-mail são realizadas pelo workflow, antes de os dados serem encaminhados ao modelo.

**Distinção importante:** Vibecode é a prática de desenvolver com apoio iterativo de ferramentas de IA, usando instruções em linguagem natural para criar ou ajustar partes da solução. O projeto também contém programação convencional em HTML, CSS e JavaScript; portanto, não deve ser descrito como uma aplicação inteiramente No Code.

Consulte [Integração e arquitetura](docs/03-integracao-e-arquitetura.md) para o fluxo detalhado.

## 6. Testes, validação e segurança

A documentação técnica do projeto descreve validações de campos, tratamento de falhas da IA, verificação de identidade no chat e cenários de teste. Entretanto, ela registra que, no momento daquele levantamento, apenas o cenário de prioridade alta havia sido marcado como aprovado com dados simulados; os demais cenários ainda estavam pendentes no registro.

Por esse motivo, este repositório não declara que todos os testes foram concluídos ou aprovados. Os resultados devem ser atualizados somente com evidências de execução.

Principais cuidados identificados:
- Validar os dados no navegador e também no workflow/servidor.
- Não confiar somente na classificação automática da IA; manter revisão humana.
- Não permitir que o chat consulte chamados sem conferir protocolo e e-mail.
- Não expor chaves ou credenciais no código da página ou no GitHub.
- Restringir o acesso à planilha, que pode conter dados pessoais.
- Proteger webhooks públicos contra abuso, spam e requisições indevidas.
- Utilizar dados fictícios nas demonstrações acadêmicas.

Mais detalhes em [Testes e segurança](docs/04-testes-e-seguranca.md).

## 7. Análise crítica

### Três vantagens
1. **Agilidade:** o editor visual do n8n e as ferramentas de IA ajudam a estruturar fluxos e integrações com menos código manual.
2. **Visualização da lógica:** condições, validações e caminhos alternativos podem ser inspecionados nos workflows.
3. **Integração:** formulário, automação, IA, planilha e e-mail trabalham em conjunto para reduzir tarefas repetitivas.

### Três limitações
1. **Dependência de serviços externos:** disponibilidade, limites de uso, custos e alterações nas APIs podem afetar o funcionamento.
2. **Possibilidade de erro da IA:** uma classificação pode estar incorreta ou não representar a gravidade real do chamado.
3. **Segurança e manutenção:** endpoints públicos, dados pessoais em planilhas e atualização manual de status exigem controles e acompanhamento.

A reflexão completa está em [Análise crítica e aprendizados](docs/05-analise-critica.md).

## 8. Relação com a etapa posterior

O protótipo de triagem de chamados foi utilizado como base para a continuidade do trabalho na etapa posterior da disciplina. Esta pasta registra os conceitos e o processo relacionados à Unidade III; a documentação do sistema e seus arquivos técnicos permanecem no repositório de projeto indicado acima.

**Repositório do projeto em grupo:** [DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder](https://github.com/DouglasSM13/Sistema-de-Triagem-automatica---Vibe-Coder)  
**Demonstração registrada no README do projeto:** [Aplicação publicada na Vercel](https://sistema-de-triagem-eosin.vercel.app/).

## 9. Organização desta unidade

- [03 — Integração e arquitetura](docs/03-integracao-e-arquitetura.md)
- [04 — Testes e segurança](docs/04-testes-e-seguranca.md)
- [05 — Análise crítica e aprendizados](docs/05-analise-critica.md)

---

*Registro acadêmico reconstruído a partir das orientações da Unidade III e da documentação técnica disponível do projeto em grupo.*
