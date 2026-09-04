---
name: instalar
description: Configura o BuilderSaaS pela primeira vez. Entrevista a empresa sobre o que ela faz, quem trabalha nela e qual processo esta doendo, preenche a memoria e devolve uma primeira proposta do que construir. Roda uma vez so.
---

# /instalar — entender a empresa

Roda **uma vez**. Transforma um BuilderSaaS genérico no sistema de UMA
empresa específica.

Isto não é ficha cadastral. É **diagnóstico**. A pessoa do outro lado tem
um problema de operação, e a entrevista existe pra achar ele.

> **Tom:** direto e objetivo, de gestor pra gestor. Nada de jargão técnico
> ("repositório", "clone", "schema"). Uma pergunta por vez.

## Antes de começar

1. Remover o vínculo com o repositório de origem, sem alarde:
   `git remote remove origin` (se existir). O que a empresa criar não pode
   voltar pro repositório do produto.
2. Se `_memoria/empresa.md` já estiver preenchido, avisar que já foi
   instalado e perguntar se quer refazer ou complementar.
3. Explicar em uma frase: "Vou te fazer algumas perguntas sobre a empresa
   pra entender onde dói. No fim eu te digo o que vale construir primeiro."

## A entrevista

**Bloco 1 — A empresa** (vai pra `_memoria/empresa.md`)
- Qual o seu nome e o da empresa? O que vocês fazem?
- Quantas pessoas trabalham aí? Quem faz o quê?
- Quem é o cliente de vocês, e como ele chega?

**Bloco 2 — Onde dói** (o coração da entrevista)
- Qual processo da empresa hoje está no WhatsApp, numa planilha ou no papel?
- O que mais gera retrabalho ou informação perdida?
- Se você pudesse resolver uma coisa da operação amanhã, qual seria?
- Já aconteceu de perderem informação importante? Como foi?

Aqui, **cavar**. Se a resposta for vaga ("é tudo meio bagunçado"), pedir um
caso concreto da semana passada. É o exemplo concreto que revela o processo.

**Bloco 3 — Quem vai usar** (vai pra `_memoria/operacao.md`)
- Quem usaria esse sistema no dia a dia? Quantas pessoas?
- Essas pessoas têm facilidade com computador?
- Vão usar no computador, no celular, ou nos dois?

**Bloco 4 — O que já existe** (vai pra `_memoria/empresa.md`)
- Que ferramentas vocês já usam? (planilha, ERP, e-mail, sistema antigo)
- Tem alguma planilha que é o coração da operação hoje?
- Vocês guardam dado de cliente? Qual tipo? (importa pra LGPD)

**Bloco 5 — Como você quer** (vai pra `_memoria/decisoes.md`)
- Prefere começar pequeno e ir crescendo, ou já quer o sistema completo?
- Tem prazo ou data que importa?
- Tem alguém técnico na empresa, ou é você mesmo tocando?

## Gravar

Preencher `_memoria/empresa.md`, `_memoria/operacao.md` e
`_memoria/decisoes.md`. No fim do `CLAUDE.md`, abaixo do marcador, escrever
um bloco **"## Sobre a [empresa]"** com o resumo, o processo prioritário e
as regras específicas.

## Fechar — a primeira proposta

Não terminar com "configurado". Terminar com **uma leitura da operação**:

> "Pelo que você me contou, o gargalo é [processo]. Hoje ele roda em
> [planilha/WhatsApp], e o problema é [o que quebra]. Isso dá pra virar um
> sistema simples: [uma frase do que seria]. Umas [N] telas.
>
> Quer que eu faça o diagnóstico completo antes? Roda `/diagnostico` e eu
> mapeio tudo, mostro o que vale virar sistema e o que é melhor deixar como
> está. Ou, se você já quer ver de pé, roda `/app` e a gente começa."

Sugerir renomear a pasta pro nome da empresa.
