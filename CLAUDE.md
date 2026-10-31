# CLAUDE.md

Guidance for working in this repository.

## Project

**node-micro** — a multitenant Identity & Access Management (IAM) starter built
with NestJS microservices, Keycloak and MySQL, following a **database-per-tenant**
model. Authored by **Mustafa Fathy Abou El-Azm**.

## Architecture

The repository is a monorepo of five independently deployable NestJS services:

| Service                        | Port | Role                                                        |
| ------------------------------ | ---- | ----------------------------------------------------------- |
| `multitenancy-rest-service`    | 5000 | Public REST API gateway + Keycloak auth + Swagger           |
| `tenant-registration`          | 8875 | Tenant registration records (TCP microservice)             |
| `tenant-provisioning`          | 8878 | Per-tenant database/table/seed provisioning (TCP)          |
| `tenant-master-service`        | 8847 | Coordinates registration ↔ provisioning ↔ config (TCP)     |
| `tenant-config-service`        | 8848 | Per-tenant configuration store (TCP)                        |

Only `multitenancy-rest-service` is exposed over HTTP. The others are NestJS
microservices reached over the message transport (`@MessagePattern`). Supporting
infrastructure (MySQL, Keycloak, MailHog) is defined in `docker-compose.yml`.

## Common commands

Run from the repository root:

```bash
npm install            # installs every service (via postinstall -> install:*)
npm run build          # builds every service in parallel
npm test               # runs every service's unit tests
docker-compose up      # starts the whole platform (dev)
```

Run inside a single service directory:

```bash
npm run start:dev      # watch mode
npm run build          # nest build
npm run lint           # eslint --fix
npm test               # jest unit tests
npm run test:cov       # jest coverage
```

## Conventions

- **Language:** TypeScript, NestJS 8.
- **Formatting/linting:** ESLint + Prettier (single quotes, 2-space indent,
  trailing commas). Run `npm run lint` in a service before committing.
- **Commits:** Conventional Commits, enforced by commitlint + Husky (`.commitlintrc`).
- **Config:** each service reads its environment from `config/*.env`. Copy the
  matching `config/.env.example` when adding a new variable.
- **Tests:** Jest unit tests live in each service's `test/unit` directory. Keep
  tests deterministic — do not rely on the host timezone or current time.

## Notes

- `config/*.env` files committed here hold **development defaults only** (local
  Docker hostnames, demo passwords). Never put real secrets in them; production
  values belong in the deployment environment.
- The database-per-tenant provisioning SQL lives in
  `tenant-provisioning/src/tenant-provisioning/scripts/`.
