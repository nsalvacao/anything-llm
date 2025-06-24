# Arquitetura Técnica Detalhada

Este documento descreve a nova arquitetura proposta para simplificar o AnythingLLM.
O objetivo é manter as funcionalidades principais (chat com documentos, múltiplos provedores de LLM, agentes personalizados e gestão de workspaces) mas reduzir o número de serviços e dependências.

## Componentes Principais

### Backend (FastAPI)
- **FastAPI** provê as rotas REST e WebSocket.
- **SQLModel** com SQLite armazena utilizadores, workspaces e logs.
- **ChromaDB** gerencia os vetores para busca semântica.
- **Celery** pode ser utilizado para tarefas assíncronas de ingestão, OCR ou transcrição. Em ambientes pequenos, `BackgroundTasks` do FastAPI é suficiente.
- Endpoints documentados automaticamente via OpenAPI/Swagger.

### Frontend (Next.js)
- Aplicação React compilada com `next build`.
- Depois de compilado, o diretório `frontend/out` é servido como ficheiro estático pelo próprio FastAPI.
- Autenticação via JWT partilhada com o backend.

### Workflow de Ingestão
1. Utilizador envia documentos através do frontend.
2. Backend armazena ficheiro temporariamente e cria uma tarefa de ingestão.
3. Worker Celery processa o ficheiro (conversão, OCR, chunking) e gera embeddings com LlamaIndex.
4. Embeddings são guardados no ChromaDB e associados ao workspace.
5. O utilizador passa a poder interrogar o workspace via chat.

### Pipelines de Deploy
- **Desenvolvimento**: `uvicorn app.main:app --reload` para backend e `next dev` para frontend.
- **Produção**: `docker compose up` constrói a imagem, compila o frontend e inicia o backend.
- **CI/CD** (exemplo): pipeline GitHub Actions que testa o backend (pytest), valida lint no frontend e publica a imagem Docker.

### Dicionário de Dados (simplificado)
| Tabela          | Campos principais                                |
|-----------------|--------------------------------------------------|
| users           | id, email, password_hash, created_at             |
| workspaces      | id, user_id, name, created_at                    |
| documents       | id, workspace_id, filename, content_type         |
| chat_messages   | id, workspace_id, role (user/assistant), content |

### DFD Simplificado
```
Utilizador --> Frontend --> Backend --> ChromaDB
                                    --> SQLite
                                    --> Workers (Celery)
```

## Dependências Relevantes
- Python 3.10+
- Node.js 18+ para compilar o frontend
- Docker (opcional) para distribuição

## Passos Sugeridos para Implementação
1. Criar estrutura de pastas `backend/`, `frontend/` e `docs/`.
2. Configurar FastAPI com SQLModel e endpoints mínimos de autenticação e workspaces.
3. Integrar ChromaDB e LlamaIndex para ingestão e busca de documentos.
4. Desenvolver o frontend em Next.js consumindo as APIs.
5. Criar `Dockerfile` que instala dependências, compila o frontend e executa o backend.
6. Automatizar testes e builds com GitHub Actions.

Este guia serve como referência para construir passo a passo a solução simplificada do AnythingLLM.
