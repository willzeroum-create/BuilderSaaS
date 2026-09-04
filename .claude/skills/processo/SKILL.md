---
name: processo
description: Documenta e padroniza um processo que hoje so existe na cabeca de alguem: quem faz, em que ordem, o que pode dar errado. Use quando a empresa depender de uma pessoa so, quando forem treinar alguem novo, ou antes de informatizar um processo.
---

# /processo — tirar da cabeça e botar no papel

Empresa pequena costuma ter processo que mora na cabeça de uma pessoa. Ela
sai de férias e a operação trava. Esta skill resolve isso.

Também é o passo anterior a informatizar: **software em cima de processo
confuso é confusão mais rápida**.

## Passo 1 — extrair

Entrevistar quem executa, não quem manda. Quem faz sabe onde dói.

- Me conta o passo a passo, do começo ao fim, como se eu fosse novo aqui.
- O que você faz quando [situação comum de exceção]?
- O que costuma dar errado nessa parte?
- Tem alguma coisa que você faz e que ninguém sabe que você faz?

A última pergunta é a mais valiosa. Quase sempre revela um passo crítico
que não está em manual nenhum.

## Passo 2 — escrever

Salvar em `saidas/processo-[nome].md`:

```markdown
# Processo: [nome]

**Quem faz:** [função]
**Quando começa:** [gatilho]
**Quando termina:** [resultado]
**Quanto leva:** [tempo médio]

## O passo a passo
1. [ação] — quem: [função] — onde: [sistema/lugar]
2. ...

## O que fazer quando dá errado
- Se [situação], então [ação]

## O que só [pessoa] sabia
[O conhecimento que estava só na cabeça dela. Esta seção é o ouro
do documento.]

## Onde isso pode virar sistema
[Os passos manuais e repetitivos, marcados.]
```

## Passo 3 — validar

Mostrar pra quem executa e perguntar: "está certo assim? faltou alguma
coisa?" Documento de processo escrito sem validação de quem faz costuma
estar errado.

## Passo 4 — usar

Registrar em `_memoria/operacao.md`. Se o processo tiver passos repetitivos
claros, oferecer o `/diagnostico` ou o `/app`.

## Regra

Documentar não é criticar. Se o processo tem gambiarra, ela existe por
algum motivo. Entender o motivo antes de propor mudar.
