# AnythingLLM Personalizado

Projeto baseado no original AnythingLLM (licença MIT). Permite conversar com os seus documentos através de modelos LLM configuráveis.

## Instalação rápida
1. Clone o repositório e execute `yarn setup`.
2. Copie `server/.env.example` para `server/.env` e personalize as variáveis de LLM e vector DB.
3. Inicie `yarn dev:server`, `yarn dev:collector` e `yarn dev:frontend`.

## Desativar telemetria
Defina `DISABLE_TELEMETRY=true` em `server/.env` para impedir o envio de dados anónimos.

Modelos locais a correr em CPU podem ter impacto no desempenho. Consulte `server/storage/models/README.md` para detalhes.

## Modelos locais (CPU)
O AnythingLLM inclui modelos nativos que correm integralmente em CPU para embeddings, transcrição e geração de texto. Em computadores com poucos recursos o desempenho pode ser afectado. Para alternativas mais leves consulte `server/storage/models/README.md` ou utilize provedores externos como LMStudio ou LocalAI.


### Product Overview

AnythingLLM is a full-stack application where you can use commercial off-the-shelf LLMs or popular open source LLMs and vectorDB solutions to build a private ChatGPT with no compromises that you can run locally as well as host remotely and be able to chat intelligently with any documents you provide it.

AnythingLLM divides your documents into objects called `workspaces`. A Workspace functions a lot like a thread, but with the addition of containerization of your documents. Workspaces can share documents, but they do not talk to each other so you can keep your context for each workspace clean.

## Cool features of AnythingLLM

- 🆕 [**Full MCP-compatibility**](https://docs.anythingllm.com/mcp-compatibility/overview)
- 🆕 [**No-code AI Agent builder**](https://docs.anythingllm.com/agent-flows/overview)
- 🖼️ **Multi-modal support (both closed and open-source LLMs!)**
- [**Custom AI Agents**](https://docs.anythingllm.com/agent/custom/introduction)
- 👤 Multi-user instance support and permissioning _Docker version only_
- 🦾 Agents inside your workspace (browse the web, etc)
- 💬 [Custom Embeddable Chat widget for your website](https://github.com/Mintplex-Labs/anythingllm-embed/blob/main/README.md) _Docker version only_
- 📖 Multiple document type support (PDF, TXT, DOCX, etc)
- Simple chat UI with Drag-n-Drop functionality and clear citations.
- 100% Cloud deployment ready.
- Works with all popular [closed and open-source LLM providers](#supported-llms-embedder-models-speech-models-and-vector-databases).
- Built-in cost & time-saving measures for managing very large documents compared to any other chat UI.
- Full Developer API for custom integrations!
- Much more...install and find out!

### Supported LLMs, Embedder Models, Speech models, and Vector Databases

**Large Language Models (LLMs):**

- [Any open-source llama.cpp compatible model](/server/storage/models/README.md#text-generation-llm-selection)
- [OpenAI](https://openai.com)
- [OpenAI (Generic)](https://openai.com)
- [Azure OpenAI](https://azure.microsoft.com/en-us/products/ai-services/openai-service)
- [AWS Bedrock](https://aws.amazon.com/bedrock/)
- [Anthropic](https://www.anthropic.com/)
- [NVIDIA NIM (chat models)](https://build.nvidia.com/explore/discover)
- [Google Gemini Pro](https://ai.google.dev/)
- [Hugging Face (chat models)](https://huggingface.co/)
- [Ollama (chat models)](https://ollama.ai/)
- [LM Studio (all models)](https://lmstudio.ai)
- [LocalAI (all models)](https://localai.io/)
- [Together AI (chat models)](https://www.together.ai/)
- [Fireworks AI  (chat models)](https://fireworks.ai/)
- [Perplexity (chat models)](https://www.perplexity.ai/)
- [OpenRouter (chat models)](https://openrouter.ai/)
- [DeepSeek (chat models)](https://deepseek.com/)
- [Mistral](https://mistral.ai/)
- [Groq](https://groq.com/)
- [Cohere](https://cohere.com/)
- [KoboldCPP](https://github.com/LostRuins/koboldcpp)
- [LiteLLM](https://github.com/BerriAI/litellm)
- [Text Generation Web UI](https://github.com/oobabooga/text-generation-webui)
- [Apipie](https://apipie.ai/)
- [xAI](https://x.ai/)
- [Novita AI (chat models)](https://novita.ai/model-api/product/llm-api?utm_source=github_anything-llm&utm_medium=github_readme&utm_campaign=link)
- [PPIO](https://ppinfra.com?utm_source=github_anything-llm)

**Embedder models:**

- [AnythingLLM Native Embedder](/server/storage/models/README.md) (default)
- [OpenAI](https://openai.com)
- [Azure OpenAI](https://azure.microsoft.com/en-us/products/ai-services/openai-service)
- [LocalAI (all)](https://localai.io/)
- [Ollama (all)](https://ollama.ai/)
- [LM Studio (all)](https://lmstudio.ai)
- [Cohere](https://cohere.com/)

**Audio Transcription models:**

- [AnythingLLM Built-in](https://github.com/Mintplex-Labs/anything-llm/tree/master/server/storage/models#audiovideo-transcription) (default)
- [OpenAI](https://openai.com/)

**TTS (text-to-speech) support:**

- Native Browser Built-in (default)
- [PiperTTSLocal - runs in browser](https://github.com/rhasspy/piper)
- [OpenAI TTS](https://platform.openai.com/docs/guides/text-to-speech/voice-options)
- [ElevenLabs](https://elevenlabs.io/)
- Any OpenAI Compatible TTS service.

**STT (speech-to-text) support:**

- Native Browser Built-in (default)

**Vector Databases:**

- [LanceDB](https://github.com/lancedb/lancedb) (default)
- [PGVector](https://github.com/pgvector/pgvector)
- [Astra DB](https://www.datastax.com/products/datastax-astra)
- [Pinecone](https://pinecone.io)
- [Chroma](https://trychroma.com)
- [Weaviate](https://weaviate.io)
- [Qdrant](https://qdrant.tech)
- [Milvus](https://milvus.io)
- [Zilliz](https://zilliz.com)

### Technical Overview

> Este repositório é um fork do projeto original [Mintplex Labs/anything-llm](https://github.com/Mintplex-Labs/anything-llm).
> Está a ser trabalhado, melhorado e personalizado por **Nuno Salvação** ([nunosalvacao.pro](https://nunosalvacao.pro)).


## Guia Rápido

1. Clone o repositório e execute `yarn setup` para gerar os ficheiros `.env`.
2. Ajuste os valores dos `.env` em `server` e `frontend` com as suas chaves e configurações.
3. Para desativar a telemetria defina `DISABLE_TELEMETRY=true` nos ficheiros `.env`.
4. Arranque o projeto com `yarn dev:server` e `yarn dev:frontend`.

## Sobre o Projeto

AnythingLLM permite usar modelos de linguagem (LLMs) e bases vetoriais para criar um ChatGPT privado, capaz de processar e referenciar documentos locais ou remotos. O objetivo deste fork é disponibilizar uma versão em português de Portugal com melhorias de usabilidade e integrações adicionais.

### Funcionalidades principais
- Utilização de LLMs fechados e de código aberto.
- Gestão de documentos através de "workspaces".
- Interface web simples e pronta a personalizar.
- Possibilidade de construir agentes de IA sem código.

### Melhorias previstas
- Tradução integral da interface para português.
- Automatização do processo de instalação e atualizações.
- Integrações com serviços nacionais e europeus.
- Exemplos de agentes personalizados focados em produtividade.

## External Apps & Integrations

_These are apps that are not maintained by Mintplex Labs, but are compatible with AnythingLLM. A listing here is not an endorsement._

- [Midori AI Subsystem Manager](https://io.midori-ai.xyz/subsystem/anythingllm/) - A streamlined and efficient way to deploy AI systems using Docker container technology.
- [Coolify](https://coolify.io/docs/services/anythingllm/) - Deploy AnythingLLM with a single click.
- [GPTLocalhost for Microsoft Word](https://gptlocalhost.com/demo/) - A local Word Add-in for you to use AnythingLLM in Microsoft Word.

## Telemetry & Privacy

AnythingLLM by Mintplex Labs Inc contains a telemetry feature that collects anonymous usage information.

<details>
<summary><kbd>More about Telemetry & Privacy for AnythingLLM</kbd></summary>

### Why?

We use this information to help us understand how AnythingLLM is used, to help us prioritize work on new features and bug fixes, and to help us improve AnythingLLM's performance and stability.

### Opting out

Set `DISABLE_TELEMETRY` in your server or docker .env settings to "true" to opt out of telemetry. You can also do this in-app by going to the sidebar > `Privacy` and disabling telemetry.

### What do you explicitly track?

We will only track usage details that help us make product and roadmap decisions, specifically:

- Type of your installation (Docker or Desktop)

- When a document is added or removed. No information _about_ the document. Just that the event occurred. This gives us an idea of use.

- Type of vector database in use. This helps us prioritize changes when updates arrive for that provider.

- Type of LLM provider & model tag in use. This helps us prioritize changes when updates arrive for that provider or model, or combination thereof. eg: reasoning vs regular, multi-modal models, etc.

- When a chat is sent. This is the most regular "event" and gives us an idea of the daily-activity of this project across all installations. Again, only the **event** is sent - we have no information on the nature or content of the chat itself.

You can verify these claims by finding all locations `Telemetry.sendTelemetry` is called. Additionally these events are written to the output log so you can also see the specific data which was sent - if enabled. **No IP or other identifying information is collected**. The Telemetry provider is [PostHog](https://posthog.com/) - an open-source telemetry collection service.

We take privacy very seriously, and we hope you understand that we want to learn how our tool is used, without using annoying popup surveys, so we can build something worth using. The anonymous data is _never_ shared with third parties, ever.

[View all telemetry events in source code](https://github.com/search?q=repo%3AMintplex-Labs%2Fanything-llm%20.sendTelemetry\(&type=code)

</details>


## 👋 Contributing

- create issue
- create PR with branch name format of `<issue number>-<short name>`
- LGTM from core-team


O projeto está disponível sob a [licença MIT](./LICENSE). Pode utilizar, modificar e redistribuir livremente, mantendo sempre esta indicação de licença.

<div align="right">

[![][back-to-top]](#readme-top)


</div>

<!-- LINK GROUP -->
