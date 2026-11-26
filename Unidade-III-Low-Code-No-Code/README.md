# Unidade III — Low Code, No Code e Vibecode

**Disciplina:** Tendências em Ciência da Computação  
**Professora:** Kadidja Valéria  
**Estudante:** Nathan Ferreira dos Santos  
**Curso:** Ciência da Computação

## 1. Apresentação

A Unidade III propôs desenvolver um mini projeto funcional utilizando abordagens Low Code, No Code e Vibecode, com apoio de Inteligência Artificial. O desafio escolhido pelo grupo foi a **triagem de chamados de suporte de Tecnologia da Informação (TI)**.

A ideia começou como um protótipo para organizar solicitações de suporte: receber as informações do usuário, estruturar o chamado e apoiar sua classificação inicial. O trabalho serviu de ponto de partida para uma versão mais completa desenvolvida posteriormente na Unidade IV.

Esta documentação registra a proposta e os conceitos da etapa inicial. Ela não deve ser confundida com todas as funcionalidades que foram acrescentadas durante a evolução do projeto.

## 2. Problema e objetivo

Solicitações de suporte técnico podem chegar de maneira desorganizada, dificultando o registro, a identificação do tipo de problema e a definição de prioridade.

**Objetivo geral:** demonstrar como ferramentas de automação visual e recursos de IA podem apoiar a organização e a triagem inicial de chamados de TI.

**Objetivos específicos:**
- Definir um fluxo simples para receber solicitações de suporte.
- Organizar os dados essenciais de cada chamado.
- Explorar o uso de IA como apoio à classificação inicial.
- Conhecer a integração entre ferramentas e serviços.
- Avaliar vantagens, limitações e cuidados de segurança.

## 3. Escopo do mini projeto — Unidade III

O escopo desta etapa é a ideia inicial de triagem: receber uma solicitação, organizar suas informações e apoiar a classificação para facilitar o encaminhamento à equipe responsável.

A proposta não deve ser descrita como se já incluísse todos os recursos da versão posterior. Funcionalidades como chatbot de acompanhamento, consulta de chamados por protocolo e e-mail, registro de informações adicionais pelo chat e fluxos mais completos de notificação pertencem à evolução documentada na Unidade IV.

## 4. Escolha da abordagem e das ferramentas

O projeto explorou uma abordagem híbrida:
- **Low Code:** utilização de uma plataforma visual para estruturar etapas, condições e integrações.
- **Inteligência Artificial:** apoio à interpretação e classificação inicial das solicitações.
- **Código tradicional:** possibilidade de construir uma interface web personalizada.
- **Vibecode:** uso iterativo de instruções em linguagem natural para apoiar a criação e o ajuste de componentes, sempre com revisão humana.

O n8n foi utilizado como plataforma de automação visual na solução. A escolha se relaciona à possibilidade de conectar etapas e serviços em fluxos compreensíveis, sem desenvolver toda a integração manualmente.

## 5. Processo de desenvolvimento

O trabalho foi organizado conforme as etapas propostas na orientação da professora:

1. **Definição do desafio:** identificar a dificuldade de organizar chamados de suporte e delimitar a triagem inicial como objetivo.
2. **Escolha da plataforma:** selecionar uma ferramenta visual capaz de organizar a lógica e conectar serviços.
3. **Integração com IA e Vibecode:** experimentar instruções em linguagem natural e recursos de IA como apoio ao desenvolvimento e à classificação.
4. **Testes e segurança:** verificar entradas, resultados, falhas e a necessidade de revisão humana.
5. **Documentação:** registrar decisões, arquitetura, aprendizados e limitações.

## 6. Testes e cuidados

A validação de um protótipo deve considerar tanto o caminho esperado quanto situações de erro. Entre os cuidados relevantes estão:
- verificar se os dados recebidos estão completos;
- tratar entradas inválidas;
- não considerar a classificação da IA como decisão definitiva;
- prever comportamento controlado quando uma integração falhar;
- proteger credenciais e dados pessoais;
- utilizar dados fictícios em demonstrações acadêmicas.

Os documentos desta pasta descrevem os critérios e cuidados identificados. Não se deve afirmar que todos os testes foram aprovados sem evidências de execução.

## 7. Análise crítica

### Vantagens
1. **Agilidade:** ferramentas visuais e IA podem reduzir o tempo necessário para estruturar um protótipo.
2. **Integração:** plataformas Low Code facilitam a conexão entre diferentes serviços.
3. **Aprendizado prático:** o projeto permite compreender como interface, automação e IA podem trabalhar em conjunto.

### Limitações
1. **Dependência de serviços externos:** disponibilidade, limites e custos podem afetar o funcionamento.
2. **Possibilidade de erro da IA:** classificações automáticas precisam de validação humana.
3. **Segurança e manutenção:** integrações e dados exigem controle de acesso, testes e acompanhamento.

## 8. Evolução para a Unidade IV

A temática de triagem de chamados foi mantida na Unidade IV. A partir da ideia inicial, o grupo desenvolveu uma versão mais completa, em colaboração com Douglas, ampliando o fluxo e acrescentando funcionalidades.

Na evolução, a solução passou a contemplar:
- formulário web para abertura de chamados;
- geração de protocolo e validação dos dados;
- classificação assistida por IA;
- registro em Google Sheets;
- notificações por Gmail;
- chatbot com Gemini para consulta do andamento mediante protocolo e e-mail;
- registro de informações adicionais encaminhadas pelo solicitante.

Esses recursos são apresentados como evolução do projeto na Unidade IV, e não como funcionalidades que já estavam concluídas na etapa inicial da Unidade III.

**Demonstração da versão evoluída:** https://sistema-de-triagem-automatica.vercel.app/

## 9. Documentos desta unidade

- [01 — Definição do desafio](docs/01-definicao-do-desafio.md)
- [02 — Escolha da plataforma](docs/02-escolha-da-plataforma.md)
- [03 — Integração e arquitetura](docs/03-integracao-e-arquitetura.md)
- [04 — Testes e segurança](docs/04-testes-e-seguranca.md)
- [05 — Análise crítica](docs/05-analise-critica.md)
- [06 — Análise Low Code/No Code](docs/06-analise-low-code-no-code.md)

---

*Documentação acadêmica da etapa inicial do projeto de triagem de chamados, organizada conforme as orientações da Unidade III.*
