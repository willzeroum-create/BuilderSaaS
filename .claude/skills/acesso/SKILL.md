---
name: acesso
description: Define quem pode ver e fazer o que dentro do sistema: papeis, permissoes e login. Use quando o sistema tiver mais de um usuario, quando precisarem separar o que cada funcao enxerga, ou ao configurar autenticacao.
---

# /acesso — quem pode o quê

Define papéis e permissões. Todo sistema com mais de um usuário precisa
disso **desde o começo**. Deixar pra depois é como acrescentar fundação em
prédio pronto.

## Passo 1 — mapear os papéis

Partir dos cargos reais da empresa, não de nomes genéricos:

- Quem trabalha com esse processo? Que função cada um tem?
- Tem informação que só o dono pode ver? (custo, margem, salário)
- Tem alguém de fora que precisa acessar? (cliente, fornecedor, contador)
- Quando alguém sai da empresa, o que precisa acontecer?

A última pergunta importa e quase ninguém pensa nela antes.

## Passo 2 — a tabela de acesso

Montar e confirmar antes de implementar:

| Papel | Vê | Cria/edita | Não pode |
|---|---|---|---|
| Dono | tudo | tudo | — |
| Atendente | pedidos do dia | criar pedido | ver custo, apagar |
| Financeiro | valores | dar baixa | mexer em cadastro |

Regra: **começar restritivo**. É fácil liberar depois; difícil é descobrir
que a pessoa errada via a informação errada há meses.

## Passo 3 — implementar

Verificar acesso **no servidor**, sempre. Esconder o botão na tela não é
segurança: é conveniência. Quem sabe o endereço acessa igual.

Se o sistema usa Supabase, aplicar as regras no próprio banco, pra que a
proteção valha mesmo que alguém chame a API direto.

## Passo 4 — testar de verdade

Entrar como cada papel e tentar fazer o que ele **não** pode. Se conseguir,
a permissão não está valendo. Mostrar esse teste ao dono — é o que dá
tranquilidade a ele.

## Passo 5 — registrar

Gravar a tabela de acesso em `_memoria/decisoes.md`. Toda tela nova precisa
consultar ela.

## Regras

- Senha nunca guardada em texto legível
- Saída de funcionário: desativar o acesso, não apagar o histórico dele
- Acesso de pessoa de fora sempre com prazo e escopo mínimo
