# Tenant Provisioning Service

Part of the **[node-micro](../README.md)** multitenant IAM platform by Mustafa Fathy Abou El-Azm.

Provisions the per-tenant database infrastructure (database-per-tenant model).

- **Framework:** [NestJS](https://nestjs.com/) (TypeScript)
- **Transport:** NestJS Microservice (TCP)
- **Port:** `8878`

## Responsibilities

- Creates a dedicated database for a tenant.
- Creates tables within the tenant database.
- Seeds initial data.
- Exposes a `ping` health check against the tenant database.

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
