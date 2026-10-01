# 🤖 Segundo Cérebro: Integração Alexa + ChatGPT via n8n

> **Projeto prático desenvolvido para o desafio "Treinando uma IA de Aprendizagem"**

---

## 📌 1. Objetivo do Projeto
"Construir um assistente de voz inteligente integrando a Amazon Alexa ao ChatGPT via n8n, permitindo interações em linguagem natural com memória de conversa e execução de automações de produtividade."

---

## 📚 2. Curadoria de Fontes
As fontes foram selecionadas em múltiplos formatos e validadas quanto à sua confiabilidade:

1. **Documentação Oficial Alexa Skills Kit (Amazon Developer)**: Garantia dos esquemas JSON e ciclo de vida das requisições (`LaunchRequest` e `IntentRequest`).
2. **Documentação e Nodes do n8n**: Diretrizes oficiais para manipulação do gatilho `Webhook` e resposta via `Respond to Webhook`.
3. **n8n Automation Security Guide (Cyberpulse AI)**: Boas práticas de autenticação (Header Auth, Basic Auth e JWT) para proteção do endpoint.
4. **Casos Práticos e Repositórios (Ícaro da Hora / GitHub Gist)**: Modelos funcionais de automação conectando assistentes de voz a ferramentas como Google Calendar e ClickUp.
5. **Artigo Científico "AI Powered Voice Agent Using NLP and ASR"**: Validação acadêmica sobre latência, acurácia de intenções e orquestração de LLMs.

---

## 🎯 3. Diretriz de Comportamento (System Prompt)
* "Atue como um especialista em automação e assistentes de voz. Responda com base estrita nas fontes fornecidas, priorizando instruções claras, formatos JSON compatíveis com síntese de voz (sem emojis ou quebras de linha que quebrem o TTS) e boas práticas de segurança."

---

## 🔍 4. Evidências de Validação e Testes com Citações

### Pergunta 1: Qual o tipo de Slot ideal para capturar perguntas abertas na Alexa?
* **Resposta**: O tipo de slot ideal é o `AMAZON.SearchQuery`, pois ele é projetado para capturar frases de texto aberto e perguntas sem estrutura fixa.
* **Evidência**: Documentação *How to Connect Alexa to Gemini/ChatGPT* (GitHub Gist).

### Pergunta 2: Como gerenciar a memória da conversa no n8n sem usar banco de dados externo?
* **Resposta**: Utiliza-se o nó `Simple Memory` (Window Buffer) conectado ao nó `AI Agent`, configurando o `sessionKey` dinamicamente com o `sessionId` recebido na requisição da Alexa (`{{ $json.body.session.sessionId }}`).
* **Evidência**: Discussões da comunidade n8n e especificações do n8n AI Agent.

### Pergunta 3: Quais as principais formas de proteger um webhook público no n8n?
* **Resposta**: As três formas nativas são *Header Auth* (chave no cabeçalho), *Basic Auth* (usuário e senha) e *JWT Token Auth* (tokens assinados com controle de acesso e expiração).
* **Evidência**: *n8n Automation Security Guide*.

---

## 📦 5. Materiais de Apoio Incluídos
- `chatgpt-alexa-n8n-passo-a-passo.pptx`: Apresentação PowerPoint editável com os 7 passos da integração.
- `podcast-resumo-integracao.mp3`: Resumo em áudio estilo Podcast explicando o projeto.
