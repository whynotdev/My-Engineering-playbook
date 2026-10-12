# 03 — Cloud and DevOps

## Planned reference pages

- Docker fundamentals and production images
- CI/CD with GitHub Actions
- Environment and secret management
- AWS / Azure / Google Cloud service mapping
- Infrastructure as Code
- Logging, metrics, tracing, and alerting
- Backup and disaster recovery
- Release strategies: rolling, blue-green, canary
- Kubernetes: when it is worth operating

## Delivery pipeline

```mermaid
flowchart LR
    A[Pull request] --> B[Lint and tests]
    B --> C[Build artifact/image]
    C --> D[Security and dependency checks]
    D --> E[Deploy to staging]
    E --> F[Smoke/integration tests]
    F --> G[Approval or policy gate]
    G --> H[Production deployment]
    H --> I[Health checks and rollback path]
```

Keep production credentials out of repository files. Use short-lived or federated credentials where supported.
