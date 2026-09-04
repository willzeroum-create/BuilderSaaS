---
name: lgpd
description: Verifica que dados pessoais a empresa guarda, se estao protegidos e o que falta para estar em conformidade com a LGPD. Use quando o sistema guardar dado de cliente ou funcionario, antes de publicar, ou quando perguntarem sobre privacidade e conformidade.
---

# /lgpd — os dados das pessoas

Toda empresa que guarda nome, telefone ou e-mail de cliente está sujeita à
LGPD. Não é assunto só de empresa grande.

> **Aviso obrigatório, dito ao usuário:** isto é uma verificação prática de
> boas práticas, não é parecer jurídico. Para situação sensível — dado de
> saúde, dado de criança, volume grande — a empresa deve consultar um
> advogado. Nunca afirmar que a empresa "está em conformidade"; dizer o que
> foi verificado e o que falta.

## Passo 1 — inventário

Levantar, sem julgar:

- Que dado de pessoa o sistema guarda? (nome, CPF, telefone, endereço)
- Tem dado sensível? (saúde, biometria, opinião política, religião)
- Guarda dado de menor de idade?
- De onde vem esse dado? A pessoa sabe que vocês guardam?
- Quem dentro da empresa consegue ver?
- Por quanto tempo fica guardado?

Montar a tabela em `saidas/dados-pessoais.md`:

| Dado | Por que a empresa precisa | Quem acessa | Tempo guardado |
|---|---|---|---|

A coluna do porquê é a mais importante. Dado guardado "porque sim" é o
primeiro a virar problema, e o mais fácil de eliminar.

## Passo 2 — verificar o básico

- Só coleta o necessário, ou pede dado que nunca usa?
- Está protegido? Senha com criptografia, acesso por papel, conexão segura?
- Backup também está protegido?
- Existe caminho pra atender quem pedir os dados dele, ou pedir exclusão?
- Se vazasse, a empresa saberia? Tem registro de quem acessou o quê?

## Passo 3 — o relatório

Listar o que está certo, o que falta e o risco de cada pendência, em
linguagem de dono, não de advogado:

```markdown
## Em ordem
- [o que já está bem]

## Falta resolver
| O que | Por que importa | Esforço |
|---|---|---|

## Recomendo conversar com um advogado sobre
- [os pontos que passam do técnico]
```

## Passo 4 — corrigir o que é técnico

Parte é resolvível na hora: apagar coluna que ninguém usa, restringir
acesso, criptografar, criar rotina de exclusão. Fazer isso, com aprovação.

Parte não é técnica — política de privacidade, base legal, contrato com
fornecedor. Nesses, apontar e recomendar apoio jurídico.

## Regras

- Menos dado guardado é sempre melhor. Se não usa, não guarde.
- Dado pessoal nunca vai pro repositório de código
- Dado de teste não pode ser dado real de cliente
- Nunca dizer que a empresa está em conformidade. Dizer o que foi
  verificado e o que ficou pendente.
