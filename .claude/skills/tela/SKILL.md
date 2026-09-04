---
name: tela
description: Acrescenta uma tela ou funcao nova ao sistema que ja existe, sem quebrar o que esta funcionando. Use quando quiserem adicionar uma funcionalidade, uma pagina, um cadastro ou um filtro no sistema.
---

# /tela — acrescentar ao sistema

Adiciona uma peça ao sistema existente sem quebrar o que já roda.

## Passo 1 — situar

Ler `_memoria/decisoes.md` e olhar `app/`. Entender o padrão que já existe:
como as outras telas são feitas, como os dados são acessados, como o acesso
é verificado. **Seguir o padrão da casa**, não introduzir um jeito novo.

Se a tela nova não couber no padrão atual, dizer isso antes de construir e
propor o ajuste.

## Passo 2 — combinar

Em três linhas, antes de codar:

> "Entendi. A tela de [nome] vai: [o que faz]. Quem acessa: [papéis]. Ela
> vai precisar guardar [campo novo], então mexe na estrutura de dados.
> Confirma?"

Se mexer na estrutura de dados, avisar explicitamente e oferecer salvar um
ponto de retorno antes.

## Passo 3 — construir

Construir só a tela combinada. Não aproveitar a viagem pra "melhorar" outra
coisa sem pedir — isso quebra confiança e dificulta achar o que causou um
problema depois.

## Passo 4 — verificar

Rodar, testar o caminho principal e pelo menos um caminho de erro (campo
vazio, dado inválido, usuário sem permissão). Mostrar funcionando.

Verificar também que a tela respeita os papéis definidos em `/acesso`. Tela
nova sem verificação de acesso é o erro mais comum e o mais caro.

## Fechar

Registrar a tela em `_memoria/operacao.md` e oferecer publicar.
