# Tenant Config Service

Part of the **[node-micro](../README.md)** multitenant IAM platform by Mustafa Fathy Abou El-Azm.

Stores and serves per-tenant configuration.

- **Framework:** [NestJS](https://nestjs.com/) (TypeScript)
- **Transport:** NestJS Microservice (TCP)
- **Port:** `8848`

## Responsibilities

- Retrieves a tenant's configuration (`get_config`).
- Updates a tenant's configuration (`update-config`).

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
