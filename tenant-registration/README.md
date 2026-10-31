# Tenant Registration Service

Part of the **[node-micro](../README.md)** multitenant IAM platform by Mustafa Fathy Abou El-Azm.

Handles the lifecycle of tenant registration records and coordinates with the Tenant Master Service.

- **Framework:** [NestJS](https://nestjs.com/) (TypeScript)
- **Transport:** NestJS Microservice (TCP)
- **Port:** `8875`

## Responsibilities

- Registers new tenants and stores their core registration record.
- Validates database-name availability for a tenant.
- Resolves a tenant's client id / secret.
- Lists tenants, updates their description, and performs soft deletes.

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
