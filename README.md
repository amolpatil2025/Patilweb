# PatilWeb Platform

Monorepo for the PatilWeb.com public website, client portal, admin area, and REST API.

## Stack

- Angular (standalone) — `apps/web`
- Node.js + Express (TypeScript) — `apps/api`
- MySQL 8+ — `database/` + `infra/docker`
- Shared DTOs — `packages/shared-contracts`

## Quick start

### 1. Environment

```bash
cp .env.example .env
```

### 2. MySQL (Docker)

```bash
docker compose -f infra/docker/docker-compose.yml up -d
```

### 3. Install and migrate

```bash
npm install
npm run build -w @patilweb/shared-contracts
npm run migrate
```

### 4. Run locally

```bash
# API — http://localhost:3000/api/v1/health
npm run dev:api

# Web — http://localhost:4200
npm run dev:web
```

## Useful scripts

| Script | Purpose |
| --- | --- |
| `npm run lint` | Lint workspaces |
| `npm run typecheck` | Typecheck workspaces |
| `npm run test` | Run tests |
| `npm run build` | Build contracts, API, and web |
| `npm run migrate` | Apply SQL migrations |

## Documentation

- [Implementation plan](PatilWeb_Cursor_Implementation_Plan.md)
- [Implementation status](docs/IMPLEMENTATION_STATUS.md)
- [Discovery](docs/discovery/route-inventory.md)
- [Architecture decisions](docs/architecture/decisions.md)

## Phase status

Phase 0 (discovery) and Phase 1 (foundation) are the current milestone. Design system and public pages start after review (Phase 2).
