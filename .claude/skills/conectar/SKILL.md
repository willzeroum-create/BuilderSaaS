---
name: conectar
description: Ensina a empresa a ligar o BuilderSaaS nas ferramentas que ela usa: banco de dados, GitHub, monitoramento, e-mail, cobranca. Ja vem tudo pre-programado com link, custo e passo a passo. Use quando quiserem conectar uma ferramenta ou perguntarem se o sistema acessa banco, e-mail ou pagamento.
---

# /conectar — ligar nas ferramentas da empresa

**Ensinar, não fazer escondido.** As conexões já vêm pré-programadas, mas o
valor está em a pessoa aprender a instalar. Depois da primeira, ela liga
qualquer outra sozinha, em qualquer projeto.

O catálogo está em `conectores/catalogo.md` e é a **única** fonte de
endereços. Nunca inventar URL.

## Tom

Nunca dizer "MCP". Dizer **conexão** ou **ligar o sistema na conta**.
Falar pelo resultado:

> "Quer ligar o sistema no banco de dados? Com isso eu consigo criar as
> tabelas do seu sistema e já deixar login e permissão prontos. A gente já
> tem o Supabase pré-configurado aqui. Te ensino a instalar, leva dois
> minutos."

## Passo 1 — oferecer o que serve

Ler `_memoria/` antes. Oferecer duas ou três, nunca a lista toda:

- Vai construir sistema com login e dados → **supabase**
- Quer histórico do código e poder voltar atrás → **github**
- Já tem sistema no ar e quer saber quando quebra → **sentry**
- A operação vive no e-mail → **gmail** (avisar que é o mais trabalhoso)
- O sistema vai cobrar do cliente → **stripe**
- Já tem um banco Postgres rodando → **banco-existente**

## Passo 2 — a conta

Mandar **o link** do catálogo e dizer o **custo antes**:

> "Primeiro você precisa de uma conta no Supabase. Cria aqui: [link].
> O plano grátis dá conta de sistema interno de empresa pequena
> tranquilamente. Se crescer, aí você avalia o pago."

Esperar confirmação de que tem a conta antes de seguir.

## Passo 3 — ensinar o comando

Mostrar a linha do catálogo, explicar, e deixar escolher:

> "É uma linha só. Ela avisa o Claude Code onde fica a ferramenta e guarda
> isso na pasta desta empresa:
>
> ```
> [comando do catálogo]
> ```
>
> Guarda essa linha: pra ligar qualquer outra ferramenta, é ela que você
> usa, mudando só o nome e o endereço.
>
> Quer colar você mesmo pra pegar o jeito, ou prefere que eu rode?"

Explicar uma vez o que cada parte faz: `--transport http` é ferramenta que
fica na internet; `--scope project` vale só pra esta empresa.

## Passo 4 — o login

> "Falta entrar na sua conta. Digite `/mcp`, escolha a conexão e faça o
> login, igual num site. A senha é digitada na tela da própria empresa, não
> aqui comigo. Me avisa quando terminar."

Uma conexão de cada vez.

## Passo 5 — provar

Nunca dizer que conectou sem testar. Fazer uma leitura inofensiva e
mostrar: listar os projetos (supabase), os repositórios (github), o nome da
conta (stripe), os últimos erros (sentry).

## Passo 6 — registrar

Entregar o link da página oficial pra pessoa guardar, e anotar em
`_memoria/empresa.md`:

```
- Conectado: Supabase (projeto [nome]). Ligado em [data].
```

## Regras que não se quebram

1. Ensinar, nunca fazer escondido. Sempre mostrar comando e link.
2. Senha nunca no chat. Se colarem uma, avisar na hora e conduzir pro `/mcp`.
3. Custo dito antes, nunca depois.
4. Banco de produção conecta em **modo leitura** por padrão. Escrita só com
   pedido explícito e depois de avisar o risco.
5. Só o que está no catálogo.
