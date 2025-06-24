# Guia para AGENTES

- Armazene prompts ou scripts de agentes personalizados em `server/utils/agents`.
- Defina as chaves de API (Google, Bing, Tavily, etc.) em `server/.env`.
- Para desativar a telemetria, use `DISABLE_TELEMETRY=true` no mesmo `.env`.
- Consulte a documentação original do AnythingLLM para integração detalhada.

# Configuracao de Agentes

Guia rapido para organizar scripts de agentes, flows e variaveis de ambiente no AnythingLLM.

## Skills personalizados

- Guarde scripts Node.js em `server/storage/plugins/agent-skills`.
- Reinicie o servidor depois de adicionar ou alterar um skill para que seja recarregado.
- Sugerimos versionar estes scripts no repositorio para facilitar colaboracao.

## Flows de agentes

- Ficheiros `.json` em `server/storage/plugins/agent-flows` definem cada flow.
- Pode criar ou editar flows pela interface **Admin > Agent Flows**, sem mexer no codigo.
- Se definir `STORAGE_DIR=/caminho/para/storage`, recrie a estrutura `plugins/agent-flows` nessa pasta.

## Variaveis de ambiente

- Copie `server/.env.example` para `.env.development` ou `.env.production` e edite conforme o ambiente.
- Configure `LLM_PROVIDER` e respectivas chaves (`OPEN_AI_KEY`, `GROQ_API_KEY`, etc.).
- Utilize `OPEN_MODEL_PREF` ou equivalente para indicar o modelo preferido.
- Defina `STORAGE_DIR` caso pretenda mudar a pasta `server/storage`.
- Consulte o `.env.example` para outras variaveis disponiveis.
- Depois de alterar o `.env`, reinicie o servidor para aplicar as mudancas.

## Telemetria

- Adicione `DISABLE_TELEMETRY=true` ao `.env` para desativar o envio de estatisticas anonimas.
- Tambem pode desligar na interface em **Sidebar > Privacy**.

