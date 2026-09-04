---
name: diagnostico
description: Mapeia os processos da empresa e mostra, com numeros, o que vale virar sistema e o que e melhor continuar como esta. Devolve um relatorio com prioridade, esforco e ganho. E o produto de entrada - use quando quiserem saber por onde comecar ou se vale a pena informatizar algo.
---

# /diagnostico — o que vale virar sistema

Mapeia a operação e devolve um relatório que serve pra decidir. Ele precisa
valer sozinho: mesmo que a empresa não construa nada, o documento é útil.

## Passo 1 — levantar os processos

Ler `_memoria/` primeiro e não repetir o que já se sabe.

Para cada área que a empresa citou, levantar os processos. Perguntar em
linguagem de operação, não de sistema:

- Me descreve o caminho de um pedido, do primeiro contato até a entrega.
- Onde essa informação fica guardada em cada etapa?
- Quem precisa saber quando algo muda?
- O que acontece hoje quando alguém erra ou esquece?
- Quantas vezes por semana isso acontece? Quanto tempo leva cada vez?

Se a pessoa não souber o número, estimar junto. **Nunca inventar número
sozinho** — número inventado destrói o relatório inteiro.

## Passo 2 — classificar

Cada processo entra em um dos quatro:

- **Vale sistema agora** — repetitivo, várias pessoas, informação que se
  perde, e o ganho paga o esforço
- **Vale depois** — o ganho existe, mas depende de outra coisa antes
- **Melhorar sem sistema** — uma planilha melhor ou um combinado resolvem
- **Não mexer** — funciona, é de baixo volume, ou é decisão humana

**Todo diagnóstico precisa ter itens nos dois últimos grupos.** É a parte
honesta, e é ela que dá credibilidade ao resto. Se tudo virou "vale sistema
agora", o diagnóstico foi mal feito.

## Passo 3 — o relatório

Salvar em `saidas/diagnostico-AAAA-MM-DD.md` e mostrar na tela:

```markdown
# Diagnóstico de operação — [empresa]
[data]

## Como a empresa opera hoje
[Dois parágrafos, com as palavras que a própria pessoa usou.
Onde a informação nasce, por onde passa, e onde ela se perde.]

## O que encontrei

| Processo | Quem faz | Frequência | Custo hoje | Veredito |
|---|---|---|---|---|
| ... | ... | ... | Xh/semana | vale sistema agora |

## Por onde começar
[Um processo só. O de maior ganho entre os de menor esforço.
O que o sistema faria, quantas telas, e o que muda no dia da equipe.]

## O que não vale informatizar
[Os honestos, com o porquê.]

## Riscos que vi
[Dado sensível sem proteção, processo que depende de uma pessoa só,
planilha sem backup. Sem alarmismo, mas sem omitir.]
```

Regras: no máximo seis processos na tabela; o custo em horas tem que bater
com o que a pessoa disse; nunca prometer prazo de construção no diagnóstico.

## Fechar

> "O relatório está em `saidas/`. Se quiser, a gente já desenha o primeiro:
> roda `/app` e eu monto a estrutura de [processo] pra você ver."

Registrar os processos mapeados em `_memoria/operacao.md`, com o veredito
de cada um.
