---
name: publicar
description: Coloca o sistema no ar e devolve o endereco pra equipe usar. Cuida de dominio, variaveis de ambiente e do que nao pode vazar. Use quando quiserem publicar, subir, colocar no ar, ou dar acesso a equipe.
---

# /publicar — colocar no ar

Sobe o sistema e devolve o endereço. É o momento em que a equipe começa a
usar de verdade, então vale conferir antes de expor.

## Passo 1 — a checagem antes de subir

Nunca publicar sem passar por aqui. Verificar e **mostrar o resultado**:

- Nenhum segredo no código. Chave, senha e token estão em variável de
  ambiente, e o `.env` está no `.gitignore`?
- O acesso está valendo? Entrar como um papel restrito e tentar o que ele
  não pode.
- Tem alguma tela ou rota aberta sem login que não deveria estar?
- Dado de teste foi removido? Publicar com "Cliente Teste 123" na base
  passa impressão ruim pra equipe.
- Existe backup? Se não existe, rodar `/backup` antes.

Se algum item falhar, **parar e resolver antes**. Publicar sistema de
empresa com falha de acesso é o pior erro possível.

## Passo 2 — escolher onde

Aplicar a regra da simplicidade:

- **Sistema interno com login** → Vercel ou Netlify + Supabase
- **Só a equipe acessa, na rede local** → servidor da própria empresa
- **Painel de leitura simples** → hospedagem estática

Perguntar antes se a empresa tem preferência ou já paga alguma hospedagem.
Não criar conta nova se já existe uma.

## Passo 3 — subir

Publicar e **confirmar que funciona de fora**: abrir o endereço, fazer
login, executar uma ação real. Não confiar no "deploy concluído".

## Passo 4 — entregar

Não terminar com jargão. Terminar com o que o dono precisa saber:

```
No ar: [endereço]

Como sua equipe entra: [caminho, primeiro acesso]
Quem tem acesso hoje: [lista]
Onde ficam os dados: [serviço, região]
Backup: [frequência, ou "ainda não configurado"]
Custo mensal: [valor real, incluindo hospedagem e banco]
```

A linha do custo é obrigatória. Ninguém gosta de descobrir cobrança depois.

## Passo 5 — registrar

Anotar em `_memoria/decisoes.md`: onde está hospedado, qual conta, e como
publicar de novo. Se a pessoa que fez sair da empresa, isso precisa estar
escrito.

## Regra

Publicação é ação que expõe pra fora. Confirmar com o dono antes de subir
pela primeira vez, e sempre que a mudança afetar quem consegue acessar o
quê.
