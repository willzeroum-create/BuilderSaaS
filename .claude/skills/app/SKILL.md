---
name: app
description: Desenha e constroi o sistema interno da empresa, uma peca por vez. Parte do processo mapeado, define as telas, monta e mostra funcionando. Use quando quiserem criar o sistema, um app interno, ou informatizar um processo.
---

# /app — construir o sistema

Constrói o software interno da empresa. Uma peça por vez, com o dono
olhando e corrigindo.

## Passo 0 — entender antes de construir

Ler `_memoria/`. Se não houver diagnóstico, **não começar a codar**: fazer
as perguntas mínimas primeiro.

- Que processo esse sistema vai atender?
- Quem vai usar, e o que cada um precisa fazer?
- Qual a informação principal que ele guarda? (pedido? cliente? tarefa?)
- O que acontece hoje sem o sistema?

Se o processo não estiver claro na cabeça do dono, ele não vai ficar claro
no software. Nesse caso, mandar pro `/diagnostico` primeiro.

## Passo 1 — desenhar antes de construir

Descrever o sistema **em português**, e só seguir com aprovação:

```
O sistema de [processo] vai ter:

Telas
1. [nome] — o que faz, quem usa
2. ...

Informação guardada
- [entidade]: [campos principais]

Quem pode o quê
- [papel]: [o que vê e faz]

O que ele NÃO vai fazer (por enquanto)
- [limites explícitos]
```

A seção do que **não** vai fazer é obrigatória. É ela que evita o sistema
inchar e nunca ficar pronto.

## Passo 2 — escolher a base

Aplicar a regra do `CLAUDE.md`: a solução mais simples que resolve.

- **Sistema interno com login e dados** → aplicação web + Supabase
- **Poucos usuários, sem login** → aplicação web simples, dados em arquivo
- **Só um painel de leitura** → página que lê a fonte existente

Não escolher tecnologia por modinha. Se a empresa não tem ninguém técnico,
peso maior ainda pra simplicidade: menos peça, menos coisa pra quebrar.

Registrar a escolha e o **porquê** em `_memoria/decisoes.md`, com data.

## Passo 3 — construir a primeira peça

**Uma tela funcionando de ponta a ponta** vale mais que dez pela metade.
Começar pela tela que a pessoa mais usa, não pela mais fácil.

Construir em `app/`, com um `README.md` dentro explicando como rodar.

Ao terminar a peça, mostrar rodando e perguntar o que mudar. Corrigir na
hora, enquanto o contexto está quente.

## Passo 4 — crescer

Cada nova tela é um `/tela`. Cada mudança de estrutura de dados é `/dados`.
Não empilhar tudo numa sessão só.

## Fechar

> "Essa parte está funcionando. Quer ver no ar pra sua equipe testar? Roda
> `/publicar`. Ou, se preferir, a gente monta a próxima tela antes."

Nunca dizer que está pronto sem ter rodado e mostrado o resultado.
