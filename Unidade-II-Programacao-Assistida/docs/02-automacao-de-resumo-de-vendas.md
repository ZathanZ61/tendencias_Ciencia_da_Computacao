# Programação Assistida e Automação com IA — Resumo de vendas

## 1. Problema
Automatizar o processamento de um lote de valores de vendas para gerar um resumo rápido com total, média, maior venda e menor venda, evitando cálculos manuais repetitivos sujeitos a erro de digitação ou soma.

## 2. Entrada
Uma lista de números representando valores de vendas (inteiros ou decimais, ex.: `[120.50, 85.00, 310.75, 49.90, 200.00]`, ou lista vazia / entradas inválidas para teste).

## 3. Processamento
Validar se a lista contém valores numéricos válidos e não está vazia; em seguida, calcular a soma total, a média aritmética, o maior valor e o menor valor usando funções nativas do Python.

## 4. Saída esperada
Um resumo estruturado exibindo:
- quantidade de vendas;
- valor total;
- valor médio;
- maior venda;
- menor venda.

## 5. Prompt utilizado
```text
Atue como desenvolvedor Python.
Contexto: Estou automatizando o resumo de valores de vendas em um script simples para uso em rotinas de conferência de caixa e relatórios.
Problema: Preciso de uma função que receba uma lista de valores numéricos de vendas e retorne um dicionário com total, média, maior valor e menor valor.
Entrada: Lista de números (int ou float).
Saída esperada: Dicionário com as chaves 'quantidade', 'total', 'media', 'maior' e 'menor' (valores arredondados para 2 casas decimais quando aplicável).
Linguagem: Python 3 (apenas biblioteca padrão).
Restrições: Não usar bibliotecas externas; tratar lista vazia ou valores não numéricos sem quebrar silenciosamente com resultado errado.
Critérios de qualidade: Código limpo, com type hints, docstring simples e fácil de ler para um estudante de Ciência da Computação.
Casos de teste: Lista com vários valores, lista com um único valor, lista vazia e valor inválido.
```

## 6. Código gerado e revisado

O prompt acima foi usado para gerar a primeira versão do script. Após a revisão humana, o código ficou assim:

```python
from collections.abc import Iterable


def resumir_vendas(vendas: Iterable[float]) -> dict:
    """Retorna quantidade, total, media, maior e menor valor de uma lista de vendas."""
    valores = list(vendas)
    if not valores:
        raise ValueError("A lista de vendas esta vazia.")

    for valor in valores:
        if isinstance(valor, bool) or not isinstance(valor, (int, float)):
            raise TypeError(f"Valor de venda invalido: {valor!r}")

    total = sum(valores)
    return {
        "quantidade": len(valores),
        "total": round(total, 2),
        "media": round(total / len(valores), 2),
        "maior": round(max(valores), 2),
        "menor": round(min(valores), 2),
    }


def exibir_resumo(vendas: Iterable[float]) -> None:
    try:
        resumo = resumir_vendas(vendas)
    except (ValueError, TypeError) as erro:
        print(f"Erro: {erro}")
        return

    print(f"Quantidade: {resumo['quantidade']}")
    print(f"Total: R$ {resumo['total']:.2f}")
    print(f"Media: R$ {resumo['media']:.2f}")
    print(f"Maior venda: R$ {resumo['maior']:.2f}")
    print(f"Menor venda: R$ {resumo['menor']:.2f}")


if __name__ == "__main__":
    casos = [
        ("Lista com varios valores", [120.50, 85.00, 310.75, 49.90, 200.00]),
        ("Lista com um unico valor", [150.0]),
        ("Lista vazia", []),
        ("Valor invalido", [100, "200"]),
        ("Booleano na lista", [100, True]),
    ]

    for nome, entrada in casos:
        print(f"--- {nome}: {entrada}")
        exibir_resumo(entrada)
```

O que a revisão humana mudou em relação à primeira sugestão:

- passou a validar o tipo de cada item, e não apenas se a lista está vazia;
- rejeitou `bool`, que em Python é subclasse de `int` e seria somado como 1 sem aviso;
- separou o cálculo (`resumir_vendas`) da apresentação no terminal (`exibir_resumo`);
- trocou a falha silenciosa por mensagem de erro explícita.

## 7. Testes executados

Execução local em 27/11/2026, Python 3.13, com dados fictícios:

| Caso | Entrada | Resultado obtido | Situação |
|---|---|---|---|
| Lista com vários valores | `[120.50, 85.00, 310.75, 49.90, 200.00]` | 5 vendas; total 766,15; média 153,23; maior 310,75; menor 49,90 | Correto |
| Lista com um único valor | `[150.0]` | 1 venda; total, média, maior e menor iguais a 150,00 | Correto |
| Lista vazia | `[]` | `Erro: A lista de vendas esta vazia.` | Correto, sem quebrar o programa |
| Valor inválido | `[100, "200"]` | `Erro: Valor de venda invalido: '200'` | Correto, com mensagem clara |
| Booleano na lista | `[100, True]` | `Erro: Valor de venda invalido: True` | Correto, sem somar `True` como 1 |

Saída do terminal:

```text
--- Lista com varios valores: [120.5, 85.0, 310.75, 49.9, 200.0]
Quantidade: 5
Total: R$ 766.15
Media: R$ 153.23
Maior venda: R$ 310.75
Menor venda: R$ 49.90
--- Lista com um unico valor: [150.0]
Quantidade: 1
Total: R$ 150.00
Media: R$ 150.00
Maior venda: R$ 150.00
Menor venda: R$ 150.00
--- Lista vazia: []
Erro: A lista de vendas esta vazia.
--- Valor invalido: [100, '200']
Erro: Valor de venda invalido: '200'
--- Booleano na lista: [100, True]
Erro: Valor de venda invalido: True
```

## 8. Análise dos resultados

Os cinco casos confirmaram o comportamento esperado: o resumo é calculado quando os dados são válidos e a entrada é recusada com mensagem explícita quando não é. O caso do booleano foi o mais instrutivo, porque não gera exceção natural em Python: sem a verificação de tipo, `[100, True]` seria somado como `101` e o erro passaria despercebido.

O script cobre o lote de vendas, mas não valida a origem dos dados. Se a lista vier de uma planilha ou de um formulário, a conversão para número precisa acontecer antes, com tratamento próprio.

## 9. Reflexão

**Onde a IA ajudou:** na estrutura inicial, na separação entre cálculo e exibição e na sugestão dos casos de teste.

**Onde precisei revisar:** a validação de tipos, o caso do `bool` e a decisão de interromper com erro em vez de devolver um resumo incompleto.

**Consigo explicar o código?** Sim. `resumir_vendas` valida a entrada e devolve um dicionário com os cinco indicadores; `exibir_resumo` trata os erros e formata a saída em reais.

## Take away

Automatizar um cálculo simples exige mais do que somar valores: é preciso decidir o que fazer com entradas inválidas. A IA acelerou a escrita, mas a verificação dos casos de limite foi o que impediu um resultado errado de parecer correto.
