# 07 — API and Integration Selection

## Pattern comparison

| Pattern | Good fit | Trade-offs |
|---|---|---|
| REST/JSON | Standard browser APIs and CRUD | Complex screens may need multiple requests |
| GraphQL | Clients need flexible data selection | Query-cost controls, caching, and authorization require care |
| gRPC | Typed internal service communication | Browser use may need additional tooling |
| WebSockets | Bidirectional real-time communication | Connection lifecycle and scaling complexity |
| Webhooks | Notify external systems | Retries, duplicate delivery, signature verification |
| Queue | Asynchronous processing | Eventual consistency, retries, and dead-letter handling |

**Default:** REST/JSON for a React + Spring Boot business application.

## Example endpoint convention

```text
GET    /api/v1/products
GET    /api/v1/products/{id}
POST   /api/v1/products
PUT    /api/v1/products/{id}
DELETE /api/v1/products/{id}
```

## API design checklist

- Use DTOs instead of exposing persistence entities directly.
- Validate inputs on the backend.
- Use stable error formats and appropriate HTTP status codes.
- Paginate large result sets.
- Define compatibility and deprecation policies.
- Enforce authorization server-side.
- Set timeouts for outbound calls.
- Use idempotency for retry-prone operations such as payment initiation.
- Document contracts with OpenAPI when useful.
- Do not leak secrets or sensitive personal data in errors/logs.

## Synchronous vs asynchronous

Use synchronous calls when the user needs an immediate result and the operation can complete within the latency budget. Use background processing when work is slow, retryable, or does not need to block the response.

For critical database updates followed by events, evaluate a transactional outbox. Consumers should be idempotent because duplicate delivery can occur.
