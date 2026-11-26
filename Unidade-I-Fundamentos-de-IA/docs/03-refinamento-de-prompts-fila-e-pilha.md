# Atividade - Refinamento de Prompts

## Identificação
- **Nome:** Nathan Ferreira dos Santos
- **RGM:** 32114001
- **Disciplina:** Tendências em Ciência da Computação
- **Data:** 25/11/2026
- **Ferramenta de IA utilizada:** Gemini

---

## Problema escolhido

### Contexto
Estou estudando estruturas de dados na graduação e quero deixar bem claro quando escolher uma fila (FIFO) ou uma pilha (LIFO) ao desenvolver sistemas simples, como filas de atendimento ou controle de tarefas.

### Problema
Diferenciar na prática **Fila (FIFO)** e **Pilha (LIFO)** e entender em quais situações de software cada estrutura se aplica melhor sem gerar dúvida.

### Objetivo
Obter uma explicação direta e organizada que mostre o funcionamento de cada estrutura, exemplos reais de uso e um critério prático de escolha.

---

## Prompt 1

### Prompt
Explique fila e pilha na programação.

### Resultado
Na programação, fila e pilha são estruturas de dados lineares usadas para organizar elementos. Uma fila funciona com a lógica FIFO (First In, First Out), onde o primeiro elemento a entrar é o primeiro a sair, como uma fila de banco. Já a pilha funciona com a lógica LIFO (Last In, First Out), onde o último elemento a entrar é o primeiro a sair, como uma pilha de pratos. Ambas possuem operações básicas de inserção e remoção e são usadas em diversos algoritmos e sistemas.

### Análise
- **O que funcionou?** Deu uma noção básica das siglas FIFO e LIFO e trouxe exemplos visuais simples.
- **O que faltou?** Faltaram exemplos mais ligados a sistemas computacionais e critérios para decidir quando usar cada uma.
- **O que ficou genérico?** Falar apenas em "operações básicas" e "diversos algoritmos e sistemas" não ajuda muito na hora de escolher uma estrutura.
- **O que poderia ser melhor?** Especificar para quem é a explicação, pedir exemplos reais de software e estruturar a comparação.

---

## Prompt 2

### Alterações realizadas
- **Papel:** Professor de Estrutura de Dados.
- **Contexto:** Explicação voltada para estudantes iniciantes de Ciência da Computação.
- **Objetivo:** Mostrar na prática a diferença entre Fila e Pilha em sistemas.
- **Público:** Estudantes iniciantes de programação.
- **Formato:** Tópicos e tabela comparativa.
- **Restrições:** Até cerca de 350 palavras, sem código extenso.
- **Critérios:** Linguagem simples e exemplos reais de computação.

### Prompt
Atue como professor de Estrutura de Dados para estudantes iniciantes de Ciência da Computação.
Explique a diferença entre Fila (FIFO) e Pilha (LIFO) com foco em aplicações reais de computação.
Inclua:
1. Definição simples de cada estrutura;
2. Dois exemplos práticos de uso em sistemas;
3. Uma tabela comparando ordem de saída, uso principal e vantagem.
Limite a resposta a cerca de 350 palavras e evite códigos extensos.

### Resultado
**Fila (FIFO - First In, First Out):** O primeiro item inserido é o primeiro removido.
- *Exemplos em sistemas:* fila de impressão e fila de processamento de requisições/mensagens.

**Pilha (LIFO - Last In, First Out):** O último item inserido é o primeiro removido.
- *Exemplos em sistemas:* histórico de navegação/desfazer ações (`Ctrl+Z`) e pilha de chamadas de funções.

| Critério | Fila (FIFO) | Pilha (LIFO) |
|---|---|---|
| Ordem de saída | Primeiro que entra, primeiro que sai | Último que entra, primeiro que sai |
| Uso principal | Atendimento por ordem de chegada | Reversão, retorno e desfazer |
| Vantagem | Justiça/ordem cronológica | Acesso rápido ao evento mais recente |

---

## Comparação

| Critério | Prompt 1 | Prompt 2 |
|---|---:|---:|
| Clareza | 3 | 5 |
| Precisão | 4 | 5 |
| Relevância | 2 | 4 |
| Organização | 3 | 5 |
| Adequação ao público | 3 | 4 |
| Atendimento ao objetivo | 2 | 4 |

---

## Prompt 3

### O que ainda precisava melhorar?
A resposta do Prompt 2 ficou boa, mas ainda faltava mostrar uma situação em que nenhuma das duas estruturas sozinha resolve bem e um pequeno caso para eu testar o raciocínio.

### Hipótese
Acredito que a resposta ficará melhor porque incluir limitações de cada estrutura e um cenário prático vai deixar a aplicação mais clara no dia a dia.

### Prompt
Atue como professor de Estrutura de Dados para estudantes iniciantes de Ciência da Computação.
Contexto: Estou aprendendo estruturas lineares e quero decidir entre Fila (FIFO) e Pilha (LIFO) ao modelar sistemas simples.
Objetivo: Ajudar a escolher a estrutura correta com segurança.

Apresente:
1. Resumo objetivo de Fila (FIFO) e Pilha (LIFO);
2. Tabela comparativa (ordem de saída, aplicação real em software, limitação principal);
3. Uma situação em que nenhuma das duas sozinha basta (ex.: atendimento com prioridade);
4. Um mini-cenário problema para testar a escolha da estrutura (sem dar a resposta pronta).

Restrições:
- Máximo de 400 palavras;
- Explicar termos técnicos na primeira vez que aparecerem;
- Tom direto e didático.

### Resultado
**Fila (FIFO - First In, First Out):** Segue a ordem de chegada; quem entra primeiro sai primeiro. Útil em filas de tarefas e atendimento sequencial.

**Pilha (LIFO - Last In, First Out):** Prioriza o item mais recente; o último que entra é o primeiro a sair. Útil em desfazer operações e retorno de execuções.

| Critério | Fila (FIFO) | Pilha (LIFO) |
|---|---|---|
| Ordem de saída | Mais antigo primeiro | Mais recente primeiro |
| Aplicação real em software | Fila de jobs / envio de notificações | Botão voltar / desfazer (`undo`) |
| Limitação principal | Não atende urgências à frente sem fila de prioridade | Itens antigos ficam bloqueados no fundo |

**Quando nenhuma das duas sozinha basta:** Em um sistema de triagem ou suporte com urgências críticas, uma fila FIFO simples pode atrasar casos graves, exigindo fila de prioridade ou outras estruturas.

**Mini-cenário para testar:** Um editor de texto precisa registrar cada alteração feita pelo usuário para permitir desfazer a última ação. Qual estrutura você escolheria e por quê?

---

## Comparação final

| Critério | Prompt 1 | Prompt 2 | Prompt 3 |
|---|---:|---:|---:|
| Clareza | 3 | 5 | 5 |
| Precisão | 4 | 5 | 5 |
| Relevância | 2 | 4 | 5 |
| Organização | 3 | 5 | 5 |
| Adequação ao público | 3 | 4 | 5 |
| Atendimento ao objetivo | 2 | 4 | 5 |
| Utilidade | 2 | 4 | 5 |

---

## Validação

Como você verificou a qualidade e correção da resposta?

Revisei os conceitos de FIFO e LIFO com base no que estudo na disciplina e em referências básicas de estruturas de dados, conferindo se os exemplos de uso (filas de tarefas/impressão e desfazer ações/pilha de chamadas) fazem sentido na prática e se não havia informações inventadas.

---

## Reflexão

### 1. Qual foi a principal diferença entre os prompts?
A mudança de um pedido curto e solto para uma instrução com papel, contexto, objetivo definido, formato e restrições.

### 2. Quais elementos tiveram maior impacto?
Definir o público, pedir exemplos reais em software, usar tabela comparativa e, no Prompt 3, incluir limitações e um cenário prático.

### 3. Um prompt maior é necessariamente melhor?
Não. Escrever muito sem dar direção ou critério não melhora o resultado; o que importa é a clareza do que se quer.

### 4. O que ocorre quando o objetivo não é claro?
A IA acaba chutando o nível de detalhe e o formato, gerando uma resposta genérica ou fora do foco.

### 5. Quais informações são indispensáveis?
Objetivo claro, tarefa, contexto/público, formato e restrições ou critérios do que se espera.

### 6. Como essa habilidade pode ser utilizada profissionalmente?
Ajuda a estruturar comandos em automações, revisar respostas de modelos em fluxos de trabalho e evitar perda de tempo com saídas vagas ou mal formatadas.

### 7. Quais riscos existem ao confiar automaticamente na IA?
Aceitar um texto bem escrito que tenha erro conceitual, suposição errada ou informação incompleta e levar isso para código, trabalho ou decisão.

---

## Take Away

> Um bom prompt não é simplesmente um prompt longo. Ele precisa **ter objetivo claro, contexto suficiente, formato bem definido e critérios para que a resposta seja realmente útil e verificável.**

---

## Cinco recomendações

1. Definir o objetivo antes de escrever o prompt.
2. Explicar o contexto e o nível de profundidade esperado.
3. Pedir um formato organizado (tópicos, tabela ou passo a passo) quando ajudar na leitura.
4. Colocar limites claros para evitar respostas longas demais ou fora do escopo.
5. Conferir o conteúdo antes de usar em qualquer projeto ou entrega.
```[cite: 3]
