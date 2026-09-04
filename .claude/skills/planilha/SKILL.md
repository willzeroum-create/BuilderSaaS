---
name: planilha
description: Le a planilha que hoje sustenta a operacao, organiza os dados e migra pro sistema sem perder nada. Use quando a empresa tiver Excel ou Google Sheets como fonte da verdade, quando pedirem para importar dados, ou para limpar uma base bagunçada.
---

# /planilha — da planilha pro sistema

Quase toda empresa tem uma planilha que é o coração da operação. Ela
funcionou até aqui, e merece respeito: a migração não pode perder nada.

> Para ler e escrever arquivos Excel com fidelidade, vale instalar a skill
> oficial `xlsx` da Anthropic. Ver `conectores/skills-recomendadas.md`.

## Passo 1 — entender a planilha antes de mexer

Nunca importar direto. Primeiro, ler e **mostrar o que encontrou**:

- Quantas linhas e colunas, e o que cada coluna significa de verdade
- Onde os dados estão inconsistentes: data em três formatos, nome escrito
  de jeitos diferentes, coluna que virou observação livre
- Linhas duplicadas
- Fórmulas e ligações com outras abas ou arquivos
- Colunas que na verdade são status disfarçado (a famosa célula colorida)

Perguntar sobre o que não dá pra deduzir:

- Essa coluna aqui, o que ela quer dizer?
- Quando está em branco, significa o quê?
- Quem preenche isso, e quando?
- A cor da célula quer dizer alguma coisa?

A pergunta da cor parece boba e quase sempre revela uma regra de negócio
inteira que não está escrita em lugar nenhum.

## Passo 2 — combinar a limpeza

Mostrar o que vai ser normalizado e pedir aprovação:

```
Encontrei 1.240 linhas.

Vou padronizar:
- Datas: 3 formatos diferentes viram um só
- Telefone: tirar traço e parêntese, guardar só número
- "João Silva" e "joao silva" viram o mesmo cliente (14 casos)

Preciso que você decida:
- 23 linhas sem telefone: importo assim mesmo ou deixo de fora?
- Coluna "OBS" tem texto livre: mantenho como observação?
```

**Nunca decidir sozinho** o que fazer com dado ambíguo.

## Passo 3 — migrar

1. Guardar a planilha original em `dados/`, intocada. Ela é o backup.
2. Importar em lote pequeno primeiro (dez linhas), conferir na tela.
3. Só então importar tudo.
4. **Conferir a contagem**: quantas linhas na planilha, quantas no sistema,
   e explicar qualquer diferença.

## Passo 4 — fechar o ciclo

A parte que todo mundo esquece: combinar o que acontece com a planilha
antiga. Se ela continuar sendo editada em paralelo, em duas semanas a
empresa tem duas verdades diferentes.

> "A partir de agora, o certo é a equipe usar só o sistema. Quer que eu
> deixe a planilha marcada como histórica, pra ninguém editar sem querer?"

## Regras

- Nunca sobrescrever a planilha original
- Nunca importar sem mostrar a contagem antes e depois
- Se a planilha tiver dado pessoal, avisar e sugerir `/lgpd`
