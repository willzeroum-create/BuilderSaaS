---
name: relatorio
description: Transforma os dados do sistema em relatorio que a diretoria entende: numeros que importam, comparacao com o periodo anterior e o que fazer a respeito. Use quando pedirem relatorio, indicadores, dashboard ou acompanhamento de resultado.
---

# /relatorio — o número que vira decisão

Relatório bom não é o que mostra tudo. É o que faz alguém decidir alguma
coisa.

## Passo 1 — descobrir a pergunta

Nunca começar pelos dados. Começar pela decisão:

- Quem vai ler esse relatório?
- Que decisão essa pessoa precisa tomar com ele?
- O que ela faria diferente se o número viesse ruim?
- Com que frequência ela precisa ver isso?

Se a resposta da terceira pergunta for "nada", aquele número não merece
estar no relatório. Cortar sem dó.

## Passo 2 — escolher poucos números

Entre três e cinco indicadores. Mais que isso vira parede de número e
ninguém lê.

Para cada um: o número de agora, a comparação com o período anterior, e
**uma frase dizendo o que ele significa**. Número sem interpretação
transfere o trabalho pro leitor.

## Passo 3 — montar

Salvar em `saidas/relatorio-AAAA-MM-DD.md`. Estrutura:

```markdown
# [Empresa] — [período]

## O resumo em três linhas
[O que aconteceu, o que mudou, o que precisa de atenção.]

## Os números

| Indicador | Agora | Período anterior | Variação |
|---|---|---|---|
| ... | ... | ... | ... |

## O que chama atenção
[Um a três pontos, com o porquê e o que fazer.]

## De onde vieram os números
[Fonte e período exatos, pra qualquer um poder conferir.]
```

A última seção não é burocracia. É o que faz alguém confiar no relatório.

## Passo 4 — automatizar, se for recorrente

Se o relatório é semanal ou mensal, oferecer deixar automático, com entrega
no e-mail ou numa tela do sistema.

## Regras

- Nunca inventar número. Se o dado não existe, dizer que não existe.
- Nunca arredondar pra melhorar a aparência.
- Se a base tiver problema (dado faltando, período incompleto), avisar no
  topo do relatório, não no rodapé.
