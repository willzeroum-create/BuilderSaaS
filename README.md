# BuilderSaaS

> O sistema da sua empresa, construído com você, dentro do Claude Code.

Toda empresa tem aquele processo que ainda roda no WhatsApp, numa planilha
que só uma pessoa entende, ou num caderno. Funciona até certo tamanho. Aí
começa a doer: informação que some, retrabalho, ninguém sabe onde está o
que.

O BuilderSaaS resolve isso construindo **o software interno da sua
empresa**. Não é template pronto, não é mais uma assinatura de ferramenta
genérica. É um sistema feito pro seu processo, que roda no seu ambiente e
é seu.

---

## Ligando o sistema

Abra o Claude Code em qualquer pasta e cole isto no chat:

```
Clona o https://github.com/willzeroum-create/BuilderSaaS.git na pasta atual,
entra nela e roda o /instalar. Comece direto pela entrevista.
```

O `/instalar` te entrevista sobre a empresa: o que ela faz, quem trabalha
nela, que processo está doendo hoje. Não é ficha cadastral — é diagnóstico.
No fim, ele já te devolve uma proposta do que construir primeiro.

Quando terminar, renomeie a pasta pro nome da sua empresa.

---

## Como funciona, na prática

**1. Ele entende a empresa.** A entrevista pergunta sobre operação, não
sobre marketing: quantas pessoas, qual processo trava, onde a informação
se perde, o que hoje é planilha.

**2. Ele diagnostica.** O `/diagnostico` mapeia os processos e separa o que
vale virar software do que é melhor continuar como está. Nem tudo precisa
de sistema, e dizer isso faz parte do trabalho.

**3. Ele constrói junto com você.** O `/app` desenha e monta o sistema.
Uma tela por vez, com você olhando e corrigindo. Nada de entregar um
monstro pronto que ninguém pediu.

**4. Ele coloca no ar.** O `/publicar` sobe o sistema e te devolve o
endereço. Sua equipe começa a usar no mesmo dia.

**5. Ele cuida.** Backup, permissão de acesso, dados pessoais. A parte
chata que todo mundo esquece e que dá problema depois.

---

## Os comandos

**Núcleo** — o jeito de operar
`/instalar` entrevista a empresa e monta a memória · `/diagnostico` mapeia
os processos e mostra o que vale virar sistema · `/abrir` começa o dia
sabendo onde parou · `/conectar` liga o sistema nas ferramentas que a
empresa já usa · `/salvar` cria um ponto de retorno.

**Construir** — do desenho ao ar
`/app` desenha e constrói o sistema interno · `/tela` acrescenta uma tela
ou função nova · `/dados` modela como a informação fica organizada ·
`/acesso` define quem pode ver e fazer o quê · `/publicar` coloca no ar e
devolve o endereço.

**Operação** — o dia a dia da empresa
`/planilha` lê a planilha atual e migra pro sistema · `/email` conecta e
automatiza o e-mail da operação · `/relatorio` transforma os dados em
relatório que a diretoria entende · `/processo` documenta e padroniza um
processo que hoje só existe na cabeça de alguém.

**Cuidar** — o que evita dor de cabeça
`/backup` monta a rotina que protege os dados · `/lgpd` verifica que dados
pessoais a empresa guarda e se está tudo certo.

---

## As conexões

O sistema já vem com as conexões **pré-programadas**. Você não sai
procurando endereço nem tutorial: ele pergunta se você quer, manda o link
de onde criar a conta, mostra o comando e te ensina a instalar.

| Conexão | O que destrava |
|---|---|
| **Supabase** | o banco de dados do seu sistema, com login e permissão prontos |
| **GitHub** | guarda o código com histórico, e permite voltar atrás |
| **Sentry** | avisa quando algo quebra pro usuário, antes de ele reclamar |
| **Notion** | lê e escreve na base que a empresa já mantém |
| **Stripe** | cobrança e assinatura, se o sistema for vender algo |
| **Banco existente** | conecta no Postgres que a empresa já tem, em modo leitura |

O catálogo completo, com link, custo e passo a passo, está em
`conectores/catalogo.md`. Você aprende fazendo: depois da primeira, liga
qualquer uma sozinho.

**Sua senha é sua.** O login acontece na tela da própria empresa, nunca no
chat.

---

## Onde ficam as coisas

- `_memoria/` — o que o sistema sabe sobre a empresa, a operação e as decisões
- `app/` — o software que está sendo construído
- `dados/` — planilhas e exports que servem de matéria-prima
- `saidas/` — diagnósticos, relatórios e documentos gerados
- `conectores/` — o catálogo de ferramentas que o sistema sabe ligar
- `.claude/skills/` — os comandos

---

## A tese

Empresa não trava por falta de ferramenta. Trava porque o processo mora na
cabeça das pessoas e some quando elas saem de férias.

Software interno resolve isso, mas sempre foi caro demais pra empresa
pequena e média: analista, desenvolvedor, meses de projeto, e no fim entrega
algo que não era bem aquilo. O BuilderSaaS encurta isso pra uma conversa.
Você descreve a operação, ele constrói, você corrige na hora.

O sistema não substitui quem decide. Ele tira a operação do improviso.

---

## BuilderSaaS ou BuilderIA?

São produtos diferentes, pra momentos diferentes.

- **[BuilderIA](https://github.com/willzeroum-create/BuilderIA)** cuida de
  como a empresa **vende**: conteúdo, anúncio, oferta, marca.
- **BuilderSaaS** cuida de como a empresa **opera**: processo, dados,
  sistema interno, equipe.

Quem vende sozinho começa pelo BuilderIA. Quem já tem equipe e sente a
operação escorrendo pelos dedos começa por aqui.
