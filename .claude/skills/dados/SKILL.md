---
name: dados
description: Modela e organiza a informacao que o sistema guarda: o que e cada coisa, como se relacionam, e o que nao pode faltar. Use quando precisarem estruturar dados, criar tabela, mudar campo, ou quando a informacao estiver baguncada.
---

# /dados — organizar a informação

Define como a informação da empresa fica guardada. É a decisão mais cara de
desfazer, então vale pensar antes.

## Passo 1 — partir do mundo real, não do banco

Perguntar em linguagem da empresa:

- Quais são as coisas que vocês acompanham? (cliente, pedido, visita, OS)
- Uma [coisa] pode ter várias [outras]? Como é na prática?
- O que **nunca** pode faltar num cadastro desses?
- O que muda com o tempo e precisa manter histórico?

A última pergunta é a mais esquecida. Preço que muda, status que evolui,
responsável que troca: se o histórico importa, a modelagem muda.

## Passo 2 — propor em português

Antes de qualquer comando de banco:

```
Cliente
- nome, telefone, e-mail, documento
- um cliente tem vários pedidos

Pedido
- data, status, valor, quem atendeu
- pertence a um cliente
- guarda histórico de mudança de status
```

Confirmar com o dono. Ele entende do negócio e vai apontar o que faltou.

## Passo 3 — aplicar

Só depois de aprovado, criar ou alterar as tabelas.

**Se já houver dados em produção**, tratar como operação delicada:

1. Dizer quantos registros serão afetados
2. Salvar um ponto de retorno e fazer cópia dos dados
3. Mostrar o que vai acontecer, em português
4. Esperar um "pode" explícito
5. Aplicar e conferir a contagem depois

Nunca apagar coluna ou tabela com dado sem passar por isso.

## Passo 4 — registrar

Gravar em `_memoria/decisoes.md` o modelo e o **porquê** das escolhas, com
data. Em seis meses ninguém lembra por que ficou assim, e é esse arquivo
que responde.

## Regras

- Dado pessoal exige atenção extra: ver `/lgpd`
- Todo cadastro guarda quando foi criado e por quem
- Não apagar de verdade o que a empresa pode precisar auditar; marcar como
  inativo
