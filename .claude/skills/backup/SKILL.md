---
name: backup
description: Monta a rotina que protege os dados da empresa e testa se ela funciona de verdade. Use quando o sistema for pro ar, antes de qualquer migracao, ou quando perguntarem sobre seguranca e perda de dados.
---

# /backup — proteger o que importa

Backup que nunca foi testado não é backup. É esperança.

## Passo 1 — mapear o que precisa ser salvo

- **O banco de dados** — o que a empresa perderia se sumisse
- **Os arquivos enviados** — foto, documento, anexo
- **O código** — se está no GitHub, já está protegido
- **As configurações** — variáveis de ambiente, guardadas em lugar seguro
  e **fora** do repositório

Perguntar ao dono, direto: "se o sistema sumisse hoje, o que faria a
empresa parar?" A resposta define a prioridade.

## Passo 2 — definir a regra

Três perguntas que decidem tudo:

- **Com que frequência?** Quanto de trabalho a empresa aceita perder? Se a
  resposta é "nada", backup é contínuo. Se é "um dia", é diário.
- **Por quanto tempo guardar?** Erro descoberto um mês depois só se
  resolve com backup de um mês atrás.
- **Onde guardar?** Nunca no mesmo lugar do sistema. Se o servidor cair,
  cai junto.

## Passo 3 — montar

Configurar a rotina. Se o banco for Supabase, o próprio serviço já faz
backup automático em alguns planos — conferir qual o plano da empresa antes
de montar coisa por cima, e dizer a verdade se já estiver coberto.

## Passo 4 — testar restaurando

**Esta é a parte que não pode ser pulada.** Fazer uma restauração de
verdade, num ambiente separado, e conferir que os dados voltaram.

Só depois disso dizer que a empresa tem backup.

## Passo 5 — escrever o procedimento

Salvar em `saidas/backup.md`: o que é salvo, com que frequência, onde fica,
e **o passo a passo pra restaurar**. Escrito de um jeito que outra pessoa
consiga seguir num dia ruim, sem depender de quem montou.

## Regras

- Backup no mesmo servidor do sistema não conta
- Backup nunca testado não conta
- Backup com dado pessoal também precisa de proteção: ver `/lgpd`
