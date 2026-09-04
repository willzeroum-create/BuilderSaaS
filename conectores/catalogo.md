# Catálogo de conexões

> Esta é a lista **pré-programada** de ferramentas que o BuilderSaaS sabe
> ligar. A empresa não sai procurando endereço nem tutorial: o sistema
> pergunta se ela quer, manda o link, mostra o comando e **ensina a
> instalar**.
>
> Endereços conferidos em 04/09/2026. Se algum parar de funcionar, é aqui
> que se corrige. Nenhuma skill guarda endereço por conta própria.

## Como cada ficha é organizada

**Serve pra** · **Destrava** · **Onde pegar a conta** · **Página oficial**
· **Custo** · **A linha que liga** · **Cuidados**

---

## Nível 1 — ligam com login, sem chave

### 🗄️ supabase — o banco de dados do sistema

- **Serve pra:** guardar os dados do sistema, com login de usuário e
  permissão por papel já prontos.
- **Destrava:** `/app`, `/dados`, `/acesso`, `/publicar`
- **Onde pegar a conta:** https://supabase.com
- **Página oficial:** https://supabase.com/docs/guides/ai-tools/mcp
- **Custo:** o plano gratuito atende sistema interno de empresa pequena
  com folga. Acima disso, tem plano pago mensal.
- **A linha que liga:**

```
claude mcp add --transport http --scope project supabase "https://mcp.supabase.com/mcp?features=docs,account,database,debugging,development,functions,branching"
```

- **Cuidados:** é a conexão mais poderosa do catálogo, porque mexe na
  estrutura do banco. Toda alteração que afeta dado existente passa pela
  regra do `/dados`: mostrar quantos registros, salvar ponto de retorno,
  esperar aprovação.

### 🐙 github — histórico do código

- **Serve pra:** guardar o código com histórico e poder voltar atrás.
- **Destrava:** `/salvar` com backup na nuvem
- **Onde pegar a conta:** https://github.com
- **Página oficial:** https://github.com/github/github-mcp-server
- **Custo:** grátis para repositório privado de empresa pequena
- **A linha que liga** (exige um token pessoal, criado em
  `github.com/settings/tokens`):

```
claude mcp add --transport http --scope project github https://api.githubcopilot.com/mcp/ --header "Authorization: Bearer ${GITHUB_TOKEN}"
```

- **Cuidados:** o token vai numa **variável de ambiente** do computador,
  nunca escrito no arquivo. Repositório de sistema de empresa nasce
  **privado**, sempre.

### 🚨 sentry — saber quando o sistema quebra

- **Serve pra:** receber aviso quando o sistema der erro pro usuário, com o
  detalhe do que aconteceu.
- **Destrava:** manutenção depois do `/publicar`
- **Onde pegar a conta:** https://sentry.io
- **Página oficial:** https://mcp.sentry.dev
- **Custo:** plano gratuito atende empresa pequena
- **A linha que liga:**

```
claude mcp add --transport http --scope project sentry https://mcp.sentry.dev/mcp
```

- **Cuidados:** vale ligar **depois** que o sistema estiver no ar, não
  antes. Cuidado pra não enviar dado pessoal dentro da mensagem de erro.

### 📔 notion — a base que a empresa já mantém

- **Serve pra:** ler e escrever nas páginas e bancos do Notion.
- **Destrava:** `/processo` e `/relatorio` passam a trabalhar em cima do
  que a empresa já organiza
- **Onde pegar a conta:** https://www.notion.com
- **Página oficial:** https://mcp.notion.com/mcp
- **Custo:** grátis
- **A linha que liga:**

```
claude mcp add --transport http --scope project notion https://mcp.notion.com/mcp
```

- **Cuidados:** no login, liberar só as páginas que interessam.

### 💳 stripe — cobrança e assinatura

- **Serve pra:** cobrar do cliente, criar link de pagamento, acompanhar
  assinatura. Só faz sentido se o sistema for cobrar de alguém.
- **Destrava:** `/app` com cobrança, `/relatorio` de receita
- **Onde pegar a conta:** https://stripe.com
- **Página oficial:** https://docs.stripe.com/mcp
- **Custo:** a conexão é grátis; a Stripe cobra por transação
- **A linha que liga:**

```
claude mcp add --transport http --scope project stripe https://mcp.stripe.com
```

- **Cuidados:** mexe em dinheiro real. Cobrança e reembolso só com
  confirmação explícita na hora. Quem vende no Brasil por Kirvano, Kiwify
  ou Hotmart provavelmente não precisa desta.

---

## Nível 2 — exigem um passo técnico a mais

Oferecer com o aviso de que dá mais trabalho.

### 🗃️ banco-existente — o Postgres que a empresa já tem

- **Serve pra:** ler o banco de um sistema que a empresa já usa, pra montar
  relatório ou migrar dados sem mexer no original.
- **Destrava:** `/relatorio`, `/planilha`, `/diagnostico`
- **Custo:** grátis
- **A linha que liga** (roda no próprio computador):

```
claude mcp add --transport stdio --scope project banco -- npx -y @bytebase/dbhub --dsn "${DATABASE_URL}"
```

- **Cuidados obrigatórios:** usar sempre um usuário **somente leitura** na
  string de conexão. Nunca apontar pro banco de produção com usuário que
  pode escrever. A string vai em variável de ambiente, nunca no arquivo.

### 📧 gmail — ler a caixa de e-mail

- **Serve pra:** ler e organizar e-mail da operação, criar rascunho.
- **Destrava:** a parte de leitura do `/email`
- **Página oficial:** https://developers.google.com/workspace/gmail/api/guides/configure-mcp-server
- **Endereço:** `https://gmailmcp.googleapis.com/mcp/v1`
- **Custo:** grátis, mas está em **prévia para desenvolvedores** e pode mudar
- **Cuidados:** **é a conexão mais trabalhosa do catálogo.** Exige criar um
  projeto no Google Cloud e configurar credencial de autorização, o que não
  é tarefa de dono de empresa sem apoio técnico. Avisar isso antes de
  começar. Para **enviar** e-mail do sistema, não precisa disto: é bem mais
  simples, e o `/email` explica a diferença.

---

## Regras que valem pra todas

1. **Ensinar, não fazer escondido.** Mostrar o comando, dizer o que faz,
   deixar a pessoa escolher se cola sozinha. Ela precisa sair sabendo
   repetir.
2. **Sempre mandar o link** de onde criar a conta e da página oficial.
3. **Nunca inventar endereço.** Se não está aqui, não existe.
4. **Senha e token nunca no chat nem em arquivo.** Autorização pelo `/mcp`;
   token em variável de ambiente, referenciado como `${NOME}`.
5. **Custo dito antes**, nunca depois.
6. **Banco de produção em modo leitura por padrão.**
7. **Dinheiro e publicação pedem confirmação na hora.**
8. **Ligar só o que a empresa usa.** Três bem escolhidas valem mais que oito.
