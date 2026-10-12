# 08 — Caching and Messaging

## These solve different problems

- **Caching** avoids repeated expensive work or access.
- **Messaging** decouples producers and consumers and supports asynchronous processing.

## When to add Redis

Consider Redis when measurements show repeated expensive reads, database pressure, a need for shared ephemeral state, rate limiting, or an appropriate low-latency data structure.

Before adding it, define:

1. Which data is cached?
2. How stale may it be?
3. How is it invalidated?
4. What happens if Redis is unavailable?
5. Could stale data affect authorization, payments, inventory, or balances?
6. How will memory and cost be bounded?

Do not casually replace the durable system of record with a cache.

## When to add a queue

| Need | Possible starting point |
|---|---|
| Simple scheduled task | Spring scheduling or managed scheduler |
| Occasional notification | Background worker or managed queue |
| Durable asynchronous workflows | Queue with retries and dead-letter handling |
| Many consumers and replayable event streams | Evaluate Kafka or a comparable event-streaming platform |

## Reliability requirements

- Idempotent consumers
- Bounded retries with backoff
- Timeouts
- Dead-letter or poison-message handling
- Monitoring of queue depth and processing delay
- Defined ownership for replay and recovery
- No secrets or unnecessary personal data in messages/logs

Exactly-once business effects are not automatically provided by a broker. Design idempotency and transaction boundaries explicitly.

## Practical rule

Start with the simplest reliable mechanism. Add Redis or a broker when a real workload or reliability requirement justifies the extra moving parts.
