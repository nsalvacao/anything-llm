# Guia de Instalação e Uso do Anything-LLM

Este documento resume os passos essenciais para preparar e executar a aplicação Anything-LLM em modo de desenvolvimento.

## 1. Pré-requisitos
- **Node.js v18+** e **Yarn** instalados.
- Opcionalmente: **Docker** para execução em contêiner.

## 2. Clonagem do projeto
```bash
git clone https://github.com/Mintplex-Labs/anything-llm.git
cd anything-llm
```

## 3. Configuração inicial
1. Execute `yarn setup` para instalar dependências e copiar os ficheiros `.env`.
2. Edite `server/.env` conforme o seu provedor de LLM e vector DB.
3. Opcionalmente defina `DISABLE_TELEMETRY=true` para desativar a telemetria.

## 4. Execução em modo desenvolvimento
Em terminais separados, execute:
```bash
yarn dev:server
yarn dev:collector
yarn dev:frontend
```
A interface ficará disponível em `http://localhost:3001`.

## 5. Uso básico
- **Adicionar documentos**: Crie "workspaces" e faça upload dos ficheiros.
- **Configurar modelos**: Ajuste o LLM e o motor de embeddings no menu de definições.
- **Conversar**: Utilize a área de chat para interagir com os documentos carregados.

## 6. Próximos passos
- Consulte `BARE_METAL.md` para deploy sem Docker.
- Veja `docker/HOW_TO_USE_DOCKER.md` para execução em contêiner.
- Para agentes personalizados, leia `AGENTS.md`.
