# AnythingLLM Simplificado

Este repositório apresenta uma proposta de reimplementação do AnythingLLM com uma arquitetura mais enxuta baseada em **FastAPI** e **Next.js**. O objetivo é reduzir dependências e simplificar a configuração sem perder funcionalidades essenciais como chat com documentos, agentes personalizados e gestão de workspaces.

## Visão geral
- **Backend**: FastAPI com SQLModel para base de dados (SQLite por defeito) e ChromaDB para armazenamento vetorial.
- **Frontend**: Next.js servido pelo próprio backend após o processo de build.
- **Workers**: tarefas de ingestão e conversão de documentos executadas em background (Celery ou `BackgroundTasks` do FastAPI).
- **Distribuição**: imagem Docker única ou execução local via `uvicorn`.

## Instalação rápida
1. Clone o repositório.
2. Copie `server/.env.example` para `.env` e defina as chaves de API necessárias.
3. Execute `docker compose up` para levantar backend e frontend num único serviço.
   - Opcionalmente, para desenvolvimento local sem Docker:
     ```bash
     python -m venv .venv && source .venv/bin/activate
     pip install -r requirements.txt
     uvicorn app.main:app --reload
     ```
4. A aplicação ficará disponível em `http://localhost:8000`.

## Estrutura de pastas
- `backend/` – código FastAPI e workers.
- `frontend/` – aplicação Next.js.
- `docs/` – documentação (instalação, arquitetura e guias de agentes).
- `server/` – legado do AnythingLLM para referência.

## Desativar telemetria
Adicione `DISABLE_TELEMETRY=true` no ficheiro `.env` para impedir o envio de estatísticas anónimas.

## Licença
Este projeto continua sob a [licença MIT](./LICENSE).
