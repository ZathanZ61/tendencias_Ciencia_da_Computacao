## Atividades e estudos já registrados

### 1. Comparação Prática

* **Prompt Genérico:** "O que é Machine Learning?"
  * **Resposta:**
    > Machine Learning (Aprendizado de Máquina) é uma subárea da Inteligência Artificial que permite que sistemas aprendam e melhorem automaticamente a partir de dados, sem serem explicitamente programados para isso. Ele utiliza algoritmos estatísticos para identificar padrões em grandes volumes de dados e fazer previsões ou tomar decisões.

* **Prompt Estruturado (Papel + Objetivo + Contexto + Formato):** "Atue como um professor. Explique Machine Learning para um iniciante, usando analogia com esportes em 2 parágrafos."
  * **Resposta:**
    > Pense no Machine Learning como o treino de um atleta de basquete. No início, o jogador arremessa a bola várias vezes sem saber a força ou o ângulo exato, errando a maioria das tentativas. Com o tempo e com a repetição de centenas de arremessos, o cérebro do atleta ajusta os movimentos automaticamente até atingir a precisão ideal, sem que ele precise calcular a física do arremesso manualmente.
    > 
    > Da mesma forma, um algoritmo de Machine Learning analisa milhares de exemplos e dados do passado para entender o que funciona e o que não funciona. Ele ajusta seus próprios parâmetros com base nos erros e acertos do "treino" para conseguir fazer previsões precisas no futuro quando se deparar com uma situação inédita.

---

##  Análise Crítica

A resposta gerada pelo **Prompt Estruturado** foi significativamente mais útil e clara. A definição de um **Papel** (*Professor*) aliada ao uso do **Contexto** (*analogia esportiva*) permitiu traduzir um conceito abstrato em uma ideia simples e do dia a dia. Além disso, estabelecer o **Formato** (*2 parágrafos*) reduziu a ambiguidade, evitando explicações excessivamente longas ou genéricas e entregando exatamente a resposta necessária para um perfil iniciante.

---

# Atividade Prática: Identificando a IA

**Objetivo:** Mapear a presença de Inteligência Artificial em tecnologias do cotidiano, analisando onde ela atua, os problemas que resolve, os dados utilizados, os benefícios e os riscos observáveis.

---

### 1. Waze
* **Onde a IA está presente:** Nos algoritmos de roteamento preditivo e processamento de dados de trânsito em tempo real.
* **Qual problema procura resolver:** Lidar com engarrafamentos imprevistos e encontrar o caminho mais rápido para o destino.
* **Quais dados provavelmente são utilizados:** Localização via GPS em tempo real, velocidade média dos veículos, histórico de tráfego por horário e alertas reportados pelos usuários (acidentes, blitz, obras).
* **Qual é o benefício direto para o usuário:** Economia de tempo, redução do estresse e estimativa precisa do horário de chegada (ETA).
* **Existe algum risco ou limitação observável:** Viés de rotas por caminhos estreitos ou perigosos, além da dependência constante de conexão de dados/internet.
* **Fonte Oficial:** [Waze Tech Blog](https://medium.com/waze) / Central de ajuda do Waze sobre algoritmos de tráfego.

---

### 2. Nubank
* **Onde a IA está presente:** Nos sistemas de detecção de fraude, análise para concessão de crédito/limite e no suporte via assistente virtual/chatbot.
* **Qual problema procura resolver:** Reduzir fraudes financeiras instantâneas (como transações suspeitas) e automatizar o atendimento simples.
* **Quais dados provavelmente são utilizados:** Histórico de compras, padrão de gastos, dados de geolocalização da transação, comportamento de digitação/biometria e histórico de pagamentos.
* **Qual é o benefício direto para o usuário:** Aumento da segurança na conta, aprovação mais rápida de transações/crédito e suporte disponível 24/7.
* **Existe algum risco ou limitação observável:** Bloqueios temporários indevidos por "falso positivo" de fraude e dificuldade de acesso a atendimento humano em casos atípicos.
* **Fonte Oficial:** [Building Nubank (Blog de Engenharia)](https://building.nubank.com.br/) — artigos detalhando o uso de Machine Learning para fraude e crédito.

---

### 3. Uber Driver
* **Onde a IA está presente:** No algoritmo de pareamento (*match*) entre passageiro e motorista, na precificação dinâmica e no cálculo de rotas e estimativa de ganhos.
* **Qual problema procura resolver:** Maximizar a eficiência do sistema, reduzindo o tempo de espera do motorista até a próxima viagem e equilibrando oferta e demanda.
* **Quais dados provavelmente são utilizados:** Localização do motorista e passageiro, taxa de aceitação/cancelamento, histórico de trajetos, horários de pico e avaliação dos usuários.
* **Qual é o benefício direto para o usuário:** Redução do tempo ocioso entre corridas e maior previsibilidade dos ganhos ao longo do dia.
* **Existe algum risco ou limitação observável:** Flutuações imprevisíveis nos ganhos por conta do preço dinâmico e risco de viés nas avaliações do perfil do motorista.
* **Fonte Oficial:** [Uber Engineering Blog](https://www.uber.com/blog/engineering/) — cobre o funcionamento do algoritmo de matching e preço dinâmico.

---

### 4. WhatsApp
* **Onde a IA está presente:** Na transcrição automática de mensagens de áudio em texto, sugestão de respostas rápidas (*Smart Reply*), filtros de spam e na assistente Meta AI integrada ao app.
* **Qual problema procura resolver:** Agilizar a comunicação cotidiana, facilitar a leitura de áudios longos em ambientes barulhentos e barrar mensagens maliciosas/golpes.
* **Quais dados provavelmente são utilizados:** Texto da conversa (quando usado com Meta AI), metadados das mensagens (horários, frequência de envio) e amostras de áudio para conversão em texto.
* **Qual é o benefício direto para o usuário:** Praticidade na comunicação, economia de tempo ao ler áudios e ajuda instantânea para pesquisas no próprio chat.
* **Existe algum risco ou limitação observável:** Erros de transcrição em sotaques ou termos regionais e preocupações constantes dos usuários com a privacidade dos dados.
* **Fonte Oficial:** [Meta AI Research](https://ai.meta.com/blog/) / Página de privacidade do WhatsApp sobre detecção de spam.

---

### 5. Spotify
* **Onde a IA está presente:** No sistema de recomendação de músicas (como as playlists *Descobertas da Semana* e *Mix Diário*) e na funcionalidade do DJ com voz artificial.
* **Qual problema procura resolver:** Ajudar o usuário a descobrir novas músicas e artistas que combinem com seu gosto entre milhões de opções disponíveis.
* **Quais dados provavelmente são utilizados:** Histórico de reprodução, músicas curtidas/salvas, horário em que você escuta determinados gêneros, taxa de rejeição (quando você pula uma música) e playlists criadas por perfis semelhantes.
* **Qual é o benefício direto para o usuário:** Experiência musical personalizada sem a necessidade de buscar novas faixas manualmente.
* **Existe algum risco ou limitação observável:** A criação da "bolha de filtro" (o aplicativo sugerir sempre o mesmo estilo de música e limitar a diversidade de descobertas).
* **Fonte Oficial:** [Spotify Research](https://research.atspotify.com/) — artigos acadêmicos explicando os sistemas de recomendação e filtragem colaborativa.

---
