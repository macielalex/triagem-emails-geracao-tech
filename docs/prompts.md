# Engenharia de Prompts

Este documento contém o texto integral de cada prompt usado no fluxo, com as variáveis, o contexto e os exemplos de saída.

## 1. Prompt de triagem (classificação)

Usado para cada e-mail novo. Produz um JSON com prioridade, intenção, sentimento e se o e-mail pode receber resposta automática.

### Instruções do sistema

> _(a preencher)_

### Variáveis

| Variável | Origem | Descrição |
|---|---|---|
| `{{remetente}}` | cabeçalho `From` | Endereço de quem enviou |
| `{{assunto}}` | cabeçalho `Subject` | Assunto do e-mail |
| `{{corpo}}` | corpo do e-mail | Texto, sem HTML, limitado a 4000 caracteres |

### Formato de saída

> _(a preencher, com o JSON esperado)_

### Exemplos de entrada e saída

> _(a preencher, com pelo menos 3 exemplos)_

## 2. Prompt de resposta automática

Usado somente para e-mails classificados como `baixa_complexidade` e `resposta_automatica: true`.

> _(a preencher)_
