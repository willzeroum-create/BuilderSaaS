---
name: email
description: Conecta o e-mail da operacao ao sistema e automatiza o que hoje e feito na mao: aviso de pedido, cobranca, confirmacao, relatorio que chega sozinho. Use quando a operacao depender de e-mail ou quando pedirem envio automatico.
---

# /email — o e-mail da operação

Muita empresa tem o processo inteiro morando no e-mail. Esta skill traz
isso pro sistema e automatiza o que é repetitivo.

## Antes de tudo: separar dois problemas

São coisas diferentes e a confusão entre elas causa retrabalho:

- **Ler e-mail** (achar pedido, extrair dado, organizar) → precisa conectar
  na caixa de entrada. É o caminho mais trabalhoso; ver `conectores/`.
- **Enviar e-mail do sistema** (confirmação, aviso, relatório) → não precisa
  conectar caixa nenhuma. Usa um serviço de envio, e é bem mais simples.

Perguntar qual dos dois a pessoa quer antes de propor qualquer coisa. Na
maioria das vezes, ela quer o segundo e acha que precisa do primeiro.

## Enviar do sistema

1. Levantar quais mensagens o sistema precisa mandar, e **quando**:
   pedido criado, status mudou, cobrança vencendo, resumo da semana.
2. Escrever cada modelo com a voz da empresa, não com voz de robô.
3. Deixar claro quem recebe e o que acontece se o envio falhar.
4. Testar mandando pra você mesmo antes de ligar pra valer.

**Regra do disparo:** nada de envio em massa sem confirmação explícita.
Antes de qualquer disparo, mostrar quantas pessoas vão receber e o texto
exato. E-mail enviado não volta.

## Ler a caixa

Se a pessoa realmente precisa disso, conduzir pelo `/conectar` e avisar
antes que é a conexão mais trabalhosa de todas, porque exige criar
credencial no Google Cloud.

Perguntar o que ela quer extrair, e limitar o escopo ao mínimo: uma caixa,
um rótulo, um período. Acesso amplo a e-mail é risco desnecessário.

## Cuidados

- Nunca guardar senha de e-mail. A conexão é sempre por autorização.
- E-mail contém dado pessoal por natureza: ver `/lgpd`
- Todo e-mail automático precisa de um jeito de a pessoa parar de receber
- Aviso importante nunca depende só de e-mail: se for crítico, precisa
  aparecer no sistema também
