---
name: salvar
description: Cria um ponto de retorno do trabalho. Salva local por padrao, sem precisar de conta. Backup na nuvem e opcional e pode ser ligado depois. Use quando quiserem guardar o progresso, antes de mudancas grandes, ou ao fim de uma sessao.
---

# /salvar — ponto de retorno

Guarda o estado do trabalho pra dar pra voltar atrás. **Local por padrão**:
não exige conta, internet nem cadastro.

## O que fazer

1. Se ainda não houver repositório local, criar (`git init`) sem alarde.
2. Conferir o que mudou. Se houver arquivo com segredo (`.env`, chave,
   token) fora do `.gitignore`, **parar e avisar** antes de qualquer coisa.
3. Fazer o commit com uma mensagem em português que descreva o que mudou
   pro negócio, não pro código: "cadastro de cliente com busca por CPF",
   não "add component".
4. Confirmar mostrando o que foi salvo.

## Backup na nuvem

Oferecer **uma vez**, sem insistir:

> "Isso ficou salvo aqui no seu computador. Se quiser uma cópia na nuvem,
> pra não perder se o computador der problema, dá pra ligar no GitHub. É
> opcional e leva um minuto. Quer?"

Se sim, conduzir pelo `/conectar` (github) e criar o repositório
**privado** — sistema de empresa não nasce público, nunca.

## Antes de mudança grande

Ao detectar que a próxima ação é arriscada (migração de dados, mudança de
estrutura, apagar coisa), oferecer salvar antes:

> "Isso mexe em [o que]. Quer que eu salve um ponto de retorno antes?
> Se der errado, a gente volta em um comando."

## Regra

Segredo nunca vai pro commit. Se aparecer, tratar como parada obrigatória:
mostrar o arquivo, tirar do controle de versão, e avisar que a chave
exposta precisa ser trocada na origem.
