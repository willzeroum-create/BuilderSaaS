# Skills de fora que valem instalar

O BuilderSaaS traz 16 comandos próprios, feitos pra operação de empresa.
Mas existe um ecossistema aberto de skills, e algumas resolvem melhor do
que qualquer coisa que a gente escrevesse por cima.

Esta página lista as que realmente somam pra quem usa o BuilderSaaS, com a
origem de cada uma. Nenhuma delas é obrigatória.

> **Como instalar:** skills vivem em `.claude/skills/`. Copie a pasta da
> skill pra lá (vale só neste projeto) ou pra `~/.claude/skills/` (vale em
> todos os seus projetos). Muitas hoje também vêm como plugin, e aí o
> próprio Claude Code instala.

---

## Documentos de escritório — as mais úteis aqui

Mantidas pela **Anthropic**, e é difícil fazer melhor:

| Skill | Pra que serve | Combina com |
|---|---|---|
| `xlsx` | ler, criar e editar planilhas Excel de verdade, com fórmula e formatação | `/planilha`, `/relatorio` |
| `docx` | gerar documento Word com formatação séria | `/processo`, `/lgpd` |
| `pptx` | montar apresentação a partir dos dados | `/relatorio` |
| `pdf` | ler, juntar, separar e preencher PDF | `/processo`, `/planilha` |

Se a empresa vive de planilha, o `xlsx` é a primeira coisa a instalar. O
comando `/planilha` funciona sem ele, mas fica muito melhor com.

---

## Infraestrutura, quando o sistema crescer

Mantidas pelos próprios times dos produtos:

- **Supabase** — banco, autenticação e funções. Complementa a conexão que
  já está no `conectores/catalogo.md`.
- **Vercel** e **Netlify** — publicação. Ajudam no `/publicar`.
- **Sentry** — tem skill por linguagem, além da conexão.
- **Better Auth** e **Auth0** — login e autenticação, se o `/acesso` do
  sistema ficar mais exigente que o padrão do Supabase.

---

## Onde procurar mais

Diretórios que reúnem skills da comunidade e de times oficiais:

- https://github.com/VoltAgent/awesome-agent-skills — mais de mil skills,
  organizadas por categoria
- https://github.com/hesreallyhim/awesome-claude-code — seleção mais
  criteriosa, inclui plugins e ferramentas
- https://claude.ai/directory — conectores revisados pela Anthropic

---

## Antes de instalar qualquer skill de terceiro

Skill é instrução que o Claude vai seguir dentro da pasta da sua empresa.
Trate como trataria um script que alguém te mandou:

1. **Abra o `SKILL.md` e leia.** É texto simples. Se manda apagar coisa,
   enviar dado pra fora ou rodar comando que você não entende, não instale.
2. **Prefira as de time oficial.** Anthropic, Supabase, Sentry, Vercel e
   afins respondem pelo que publicam.
3. **Instale uma de cada vez** e veja se o comportamento mudou pra melhor.
4. **Nunca instale skill que peça senha ou token dentro do arquivo.**

Skill demais também atrapalha: o sistema fica lento pra escolher e começa a
misturar as coisas. Instale o que você vai usar de verdade.
