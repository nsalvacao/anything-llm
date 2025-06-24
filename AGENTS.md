# Guia de Agentes

Este projeto permite a criação de agentes de IA personalizados através de scripts armazenados em `server/utils/agents`.

- Organize os prompts ou scripts adicionais nessa pasta e versione-os no repositório.
- Copie `server/.env.example` para `.env` e defina as chaves de API necessárias (OpenAI, Google, Bing, etc.).
- Para desativar a telemetria opcional defina `DISABLE_TELEMETRY=true` no `.env`.

## Skills personalizados
- Scripts Node.js podem ser guardados em `server/storage/plugins/agent-skills`.
- Reinicie a aplicação após adicionar ou alterar um skill.

## Flows de agentes
- Ficheiros `.json` em `server/storage/plugins/agent-flows` descrevem cada flow.
- A interface de administração permite criar e editar flows sem mexer em código.
- Se alterar `STORAGE_DIR`, recrie a estrutura `plugins/agent-flows` nesse local.

## Variáveis de ambiente principais
- `LLM_PROVIDER` e respetivas chaves (`OPEN_AI_KEY`, `GROQ_API_KEY`, etc.).
- `OPEN_MODEL_PREF` ou equivalente para indicar o modelo preferido.
- `STORAGE_DIR` para mudar a localização de `server/storage`.
- Consulte o `.env.example` para todas as opções disponíveis.

Depois de alterar o `.env`, reinicie os serviços para aplicar as mudanças.
