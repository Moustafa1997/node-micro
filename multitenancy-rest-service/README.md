# Multitenancy REST Service (API Gateway)

Part of the **[node-micro](../README.md)** multitenant IAM platform by Mustafa Fathy Abou El-Azm.

The public entry point of the platform. It exposes the REST API, handles authentication and authorization through Keycloak, validates requests, and orchestrates the backing microservices over the message transport.

- **Framework:** [NestJS](https://nestjs.com/) (TypeScript)
- **Transport:** HTTP REST + Swagger
- **Port:** `5000`

## Responsibilities

- Exposes the REST API and Swagger documentation at `/api/docs`.
- Authenticates and authorizes requests against Keycloak (realms, clients, roles, resources, policies, permissions, scopes).
- Manages tenants, users, roles and permissions through the Identity & Access Management (IAM) layer.
- Delegates tenant registration, provisioning, master and config operations to the dedicated microservices.

## Installation

```bash
npm install
```

## Running the service

```bash
# development
npm run start

# watch mode
npm run start:dev

# production mode
npm run start:prod
```

> This service is usually started together with the rest of the platform via
> `docker-compose up` from the repository root.

## Testing

```bash
# unit tests
npm run test

# test coverage
npm run test:cov
```

## License

Licensed under the [Apache License 2.0](../LICENSE).
