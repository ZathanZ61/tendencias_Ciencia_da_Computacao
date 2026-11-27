# Boas práticas na colaboração humano-IA

**Disciplina:** Tendências em Ciência da Computação
**Semana do plano de aulas:** 01/10 — Boas práticas na colaboração humano-IA
**Integrante:** Nathan Ferreira dos Santos

## 1. Objetivo

Discutir limites e potencial do uso de IA na programação a partir de um estudo de caso, identificando práticas que reduzem o risco de aceitar código que executa, mas produz resultado errado.

## 2. Estudo de caso

> Cenário fictício, construído para esta atividade. Não descreve um incidente real nem pessoa identificável.

Um estagiário precisa calcular a média de notas de uma turma e pede à IA um script simples. A ferramenta devolve:

```python
def media(notas):
    try:
        return sum(notas) / len(notas)
    except Exception:
        return 0
```

O código executa sem erro em qualquer entrada, inclusive em uma lista vazia ou com valores de texto. Foi aceito na primeira tentativa porque "funcionou".

### O que a revisão encontrou

1. `except Exception` captura qualquer falha, inclusive erro de digitação no nome da variável, e devolve `0` como se fosse um resultado calculado.
2. Média `0` é um valor plausível em uma turma real, então o erro não chama atenção.
3. Lista vazia produz `ZeroDivisionError`, que é engolido pela mesma cláusula.
4. Notas em texto geram `TypeError`, também escondido.
5. O relatório final apresenta um número, e não a informação de que não havia dados.

### Versão corrigida

```python
def media(notas: list[float]) -> float:
    """Calcula a media de uma lista nao vazia de notas."""
    if not notas:
        raise ValueError("Nenhuma nota informada.")
    return round(sum(notas) / len(notas), 2)
```

A decisão sobre o que exibir ao usuário fica com quem chama a função, e não escondida dentro do cálculo.

## 3. O que o caso mostra

- Código que executa não é necessariamente código correto.
- Tratamento genérico de erro transforma defeito em resultado silencioso.
- A IA tende a priorizar "não quebrar" quando o pedido não define o comportamento esperado em caso de falha.
- A revisão exige conhecimento do domínio: só quem conhece a regra de negócio sabe que média `0` é suspeita.
- O teste com entrada vazia revela o problema em segundos.

## 4. Boas práticas adotadas

| Prática | Por quê | Como aplicar |
|---|---|---|
| Descrever objetivo, entrada, saída e restrições no prompt | Reduz respostas genéricas | Usar o formato do prompt estruturado da Unidade I |
| Revisar linha por linha antes de executar | A IA pode esconder falhas em trechos que parecem triviais | Ler o código em voz alta e explicar cada bloco |
| Testar caminho normal, limite e inválido | Um caso feliz não prova correção | Criar pelo menos um teste para cada tipo de entrada |
| Recusar `except` genérico e valor padrão que pareça resultado | Falha silenciosa é pior que erro visível | Tratar exceções específicas e informar o problema |
| Conferir bibliotecas e dependências usadas | A sugestão pode exigir pacote não previsto | Comparar com as restrições do pedido |
| Não enviar dados pessoais ou reais para a ferramenta | Privacidade e finalidade do tratamento | Usar dados fictícios em exemplos e testes |
| Registrar o que veio da IA e o que foi alterado | Transparência acadêmica e profissional | Manter a versão gerada e a versão revisada no documento |
| Assumir a responsabilidade pela entrega | A ferramenta não responde pelo resultado | Revisar, testar e saber explicar o código final |

## 5. Limites e potencial

**Potencial observado:** ganho de velocidade na estrutura inicial, sugestão de casos de teste, refatoração e explicação de trechos desconhecidos.

**Limites observados:** erros plausíveis e bem escritos, dependência de contexto fornecido, tendência a resolver o sintoma em vez da causa e risco de aceitação sem leitura.

**Posição assumida no debate:** a IA funciona melhor como par de trabalho do que como oráculo. O estudante continua responsável por decidir o comportamento esperado, testar e explicar a solução.

## 6. Reflexão

A parte mais difícil da colaboração com IA não é obter código: é desconfiar do código que já funciona. O caso mostra que o custo de revisar é menor do que o custo de apresentar um resultado errado como correto.

Também ficou claro que a qualidade do pedido define o espaço de respostas possíveis. Quando o prompt não diz o que fazer em caso de falha, a ferramenta escolhe por conta própria, e a escolha dela raramente é a mais transparente.

## 7. Take away

Usar IA para programar exige definir o comportamento esperado antes de pedir o código, testar as entradas de limite e nunca tratar falha como resultado.

## 8. Referências

- [UNESCO — Recomendação sobre a Ética da Inteligência Artificial](https://www.unesco.org/en/artificial-intelligence/recommendation-ethics)
- [NIST — AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [Python — Documentação oficial sobre erros e exceções](https://docs.python.org/3/tutorial/errors.html)
