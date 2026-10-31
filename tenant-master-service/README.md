# Tenant Master Service

Part of the **[node-micro](../README.md)** multitenant IAM platform by Mustafa Fathy Abou El-Azm.

Acts as the master coordinator between tenant registration, provisioning and configuration.

- **Framework:** [NestJS](https://nestjs.com/) (TypeScript)
- **Transport:** NestJS Microservice (TCP)
- **Port:** `8847`

## Responsibilities

- Centralizes tenant master operations.
- Bridges the registration flow with provisioning and configuration services.

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
