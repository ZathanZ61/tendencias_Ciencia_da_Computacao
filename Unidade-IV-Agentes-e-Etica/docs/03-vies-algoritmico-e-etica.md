# 03 — Viés algorítmico e responsabilidade social

## 1. Introdução

Sistemas de IA podem apoiar a triagem de chamados, mas seus resultados não são neutros nem necessariamente corretos. A qualidade da classificação depende dos dados fornecidos, das instruções utilizadas, do contexto disponível e das limitações do modelo.

No projeto, uma sugestão de categoria ou prioridade pode influenciar a ordem de atendimento. Por isso, erros e vieses precisam ser considerados como riscos operacionais e sociais.

## 2. Possíveis fontes de viés

### 2.1 Diferenças na forma de escrever

Pessoas descrevem o mesmo problema de maneiras diferentes. Um usuário pode utilizar termos técnicos; outro pode escrever com abreviações, erros ortográficos ou linguagem informal. Se o modelo interpretar melhor uma forma de escrita do que outra, chamados equivalentes podem receber classificações diferentes.

### 2.2 Vocabulário regional e acessibilidade

Expressões regionais, termos pouco comuns e mensagens ditadas por voz podem ser interpretados incorretamente. Pessoas com menor familiaridade tecnológica também podem ter dificuldade para descrever o problema com precisão.

### 2.3 Priorização inadequada

Uma descrição curta ou pouco detalhada pode levar o modelo a sugerir prioridade baixa, mesmo quando o problema causa impacto significativo. O inverso também pode ocorrer: palavras que parecem urgentes podem elevar indevidamente a prioridade.

### 2.4 Dados históricos incompletos

Se exemplos anteriores estiverem concentrados em determinados tipos de usuários, equipamentos ou problemas, as sugestões podem reproduzir essa distribuição e apresentar desempenho inferior em situações menos representadas.

## 3. Impactos possíveis

- atraso no atendimento de solicitações importantes;
- tratamento desigual de usuários que descrevem problemas de formas diferentes;
- encaminhamento incorreto para equipes;
- confiança excessiva em uma classificação automatizada;
- exposição indevida de dados pessoais;
- dificuldade de contestar uma decisão sugerida pelo sistema.

## 4. Medidas de prevenção e mitigação

1. **Revisão humana:** permitir que a equipe confirme ou altere categoria e prioridade.
2. **Critérios claros:** definir regras de prioridade com base no impacto e na urgência, não apenas em palavras isoladas.
3. **Testes variados:** avaliar mensagens curtas, longas, informais, com erros de digitação e diferentes formas de descrever o mesmo problema.
4. **Registro de correções:** acompanhar divergências entre a sugestão da IA e a classificação final feita pela equipe.
5. **Transparência:** informar que a classificação é uma sugestão automatizada.
6. **Proteção de dados:** coletar apenas o necessário, restringir acessos e evitar inserir dados pessoais desnecessários nos prompts.
7. **Possibilidade de contestação:** oferecer um caminho para o usuário solicitar revisão quando considerar o encaminhamento inadequado.

## 5. Privacidade e proteção de dados

O sistema pode lidar com nome, e-mail, descrição de incidentes e outras informações incluídas pelo solicitante. Esses dados devem ser tratados com finalidade definida e acesso restrito.

Cuidados recomendados:
- não utilizar dados reais em demonstrações acadêmicas sem necessidade e autorização;
- evitar registrar senhas, tokens ou informações sigilosas nos chamados;
- não expor dados de um usuário a outro pelo chatbot;
- proteger credenciais dos serviços integrados;
- definir quem pode consultar e atualizar a planilha;
- estabelecer retenção e descarte adequados dos registros.

## 6. Responsabilidade social e papel humano

A automação deve ampliar a capacidade de atendimento, não retirar do usuário o direito de ser ouvido. Uma classificação incorreta pode afetar o tempo de resposta e a experiência de quem solicita suporte.

A responsabilidade pelo processo não deve ser transferida integralmente ao modelo. A equipe que utiliza a ferramenta precisa supervisionar resultados, corrigir erros e avaliar impactos. A IA não conhece todo o contexto institucional e não deve tomar decisões sensíveis sem supervisão.

## 7. Reflexão crítica aplicada aos testes do projeto

Nas execuções relatadas em 26/11/2026, o sistema classificou um chamado sobre a saída de produtos como Software / Média e um relato de instabilidade de internet que afetava todo o setor como Rede/Internet / Alta. Os exemplos mostram como a classificação pode ajudar a organizar demandas distintas, mas dois casos não são suficientes para medir precisão, imparcialidade ou desempenho geral do modelo.

A prioridade sugerida tem efeito operacional: pode influenciar a ordem de atendimento e acionar uma notificação interna. Por isso, uma classificação incorreta pode atrasar um problema importante ou gerar alertas desnecessários. A equipe deve revisar a prioridade, considerar o impacto real e poder corrigir a sugestão da IA.

O principal benefício da IA no projeto é organizar informações e apoiar tarefas repetitivas. Entretanto, velocidade não é sinônimo de justiça ou precisão. Um sistema que classifica rapidamente, mas não permite correção, pode apenas automatizar erros que antes seriam percebidos por uma pessoa.

Por isso, a solução deve combinar automação, critérios transparentes, revisão humana, proteção de dados e monitoramento contínuo. O sucesso não deve ser medido somente pela quantidade de chamados processados, mas também pela qualidade das classificações e pela equidade no atendimento. Os testes com descrições equivalentes em linguagem formal, informal, regional e com erros de digitação ainda precisam ser executados para avaliar possíveis diferenças.

## 8. Referências para aprofundamento

- [Lei Geral de Proteção de Dados Pessoais — Lei nº 13.709/2018](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm)
- [UNESCO — Recomendação sobre a Ética da Inteligência Artificial](https://www.unesco.org/en/artificial-intelligence/recommendation-ethics)
- [NIST — AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)

