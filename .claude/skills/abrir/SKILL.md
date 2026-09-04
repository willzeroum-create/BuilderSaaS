---
name: abrir
description: Abre a sessao de trabalho: carrega a memoria da empresa, verifica em que pe esta o sistema em construcao, e devolve um resumo curto de onde paramos e o que faz sentido fazer hoje.
---

# /abrir — começar o dia

Carrega o contexto e devolve um ponto de partida. Curto: no máximo doze
linhas.

## O que fazer

1. Ler `_memoria/empresa.md`, `_memoria/operacao.md` e `_memoria/decisoes.md`.
2. Olhar `app/` — o que existe, o que está pela metade.
3. Ver o histórico recente (últimos commits, arquivos mudados) pra saber
   onde a última sessão parou.
4. Conferir se há algo pendente anotado em `operacao.md`.

## O resumo

```
[Empresa] · [processo em construção]

Onde paramos: [uma frase]
No ar: [o que já está publicado e sendo usado]
Em construção: [o que está pela metade]

Sugestão de hoje:
1. [a mais importante, com o porquê]
2. [a segunda]
```

Se houver algo pendente que já apareceu em sessões anteriores e não andou,
citar isso — sem cobrar, só lembrando que está parado.

Se `_memoria/` estiver vazia, não improvisar: dizer que o sistema ainda não
foi configurado e sugerir `/instalar`.
