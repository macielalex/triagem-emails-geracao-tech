# Roteiro do vídeo de demonstração (3 a 5 minutos)

Objetivo: mostrar o fluxo funcionando ponta a ponta, do e-mail recebido até a linha na planilha e a resposta enviada.

Antes de gravar:
- Caixa do projeto (`alexmaciel.geracaotech40@gmail.com`) aberta em uma aba.
- Planilha `Triagem` aberta em outra aba, vazia ou com as linhas de teste anteriores.
- Projeto do Apps Script aberto, na tela de **Execuções**.
- Um segundo navegador ou aba com a conta pessoal, para enviar os e-mails de teste.
- Gravação de tela em 1080p, com microfone limpo.

---

## Cena 1 – Apresentação (0:00 a 0:30)

**Fala:** "Este é o Agente de Triagem de E-mails. Ele monitora uma caixa do Gmail, classifica cada mensagem com IA generativa e registra o resultado no Google Sheets. Quando o caso é simples, ele responde sozinho."

**Tela:** caixa do projeto com a lista de e-mails.

---

## Cena 2 – O problema (0:30 a 0:50)

**Fala:** "A caixa recebe dúvidas, elogios, reclamações urgentes e spam, tudo junto. A equipe perde tempo lendo e encaminhando, e casos urgentes podem demorar."

**Tela:** caixa com e-mails misturados.

---

## Cena 3 – Arquitetura (0:50 a 1:30)

**Fala:** "O gatilho do Apps Script roda a cada 5 minutos. Ele busca threads novas, envia cada uma para o Gemini com o prompt de triagem, grava o resultado na planilha e, se for elegível, gera e envia a resposta com um segundo prompt."

**Tela:** diagrama Mermaid do README, renderizado no GitHub. Mostre o trecho da seção 3.

---

## Cena 4 – Engenharia de prompts (1:30 a 2:10)

**Fala:** "O prompt de triagem pede um JSON com schema fixo. As regras de decisão estão escritas no prompt e também no código. Por exemplo, reclamação nunca recebe resposta automática, mesmo que o modelo sugira o contrário."

**Tela:** `docs/prompts.md` no GitHub, na seção de instruções do sistema.

---

## Cena 5 – Caso 1: dúvida simples, resposta automática (2:10 a 2:50)

1. Na conta pessoal, envie para o projeto o e-mail: "Qual o horário de atendimento aos sábados?"
2. Aguarde a próxima execução do gatilho, ou execute `processarEmails` manualmente no editor.
3. Mostre no Gmail do projeto a resposta enviada.
4. Mostre a linha na planilha com `resposta automática: sim` e status `resposta enviada`.

**Fala:** "Essa dúvida é simples, então o agente respondeu. A planilha registra a classificação e o status."

---

## Cena 6 – Caso 2: reclamação urgente, revisão humana (2:50 a 3:30)

1. Envie: "Fui cobrado duas vezes no cartão e preciso desse valor hoje."
2. Execute ou aguarde a execução.
3. Mostre que não houve resposta automática, que a thread recebeu a etiqueta `triagem-urgente` e que a linha na planilha tem status `revisão humana`.

**Fala:** "Essa reclamação não recebeu resposta automática. Como é urgente, ficou marcada para a equipe."

---

## Cena 7 – Caso 3: spam (3:30 a 3:50)

1. Envie um e-mail de propaganda.
2. Mostre a linha na planilha com intenção `spam` e status `registrado`, sem resposta.

---

## Cena 8 – Controle e erros (3:50 a 4:15)

**Fala:** "Cada thread é marcada como processada, então não é reprocessada. Se o Gemini retornar erro temporário, o script tenta de novo. Se uma thread falhar, ela fica de fora da marcação e será tentada na próxima execução."

**Tela:** aba de Execuções com um log de sucesso. Se possível, mostre também um log de erro tratado.

---

## Cena 9 – Encerramento (4:15 a 4:40)

**Fala:** "O código, a documentação e os prompts estão no repositório. Para rodar, basta criar o projeto no Apps Script, configurar duas propriedades e executar a função de setup. Obrigado."

**Tela:** README do repositório no GitHub, com o link.

---

## Checklist antes de enviar

- [ ] Vídeo entre 3 e 5 minutos
- [ ] Nenhuma chave de API visível na tela (esconda as propriedades do script)
- [ ] E-mails de teste sem dados pessoais reais
- [ ] Link do repositório no README
- [ ] Documentação e vídeo enviados na plataforma, com status definitivo (não "Rascunho")
