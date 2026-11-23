---
name: backend-development
description: Design, implement, test, and review backend services, APIs, databases, and distributed workflows.
---

# Backend Development

Use this skill when designing or changing backend services.

## Workflow
1. Establish requirements, consumers, data ownership, latency, throughput, availability, and security constraints.
2. Define API contracts before implementation. Prefer explicit schemas, stable error formats, pagination, versioning, and idempotency where appropriate.
3. Keep transport, application, domain, and persistence responsibilities separated.
4. Validate inputs at trust boundaries. Apply authentication, authorization, rate limits, secret handling, and least privilege.
5. Design database constraints and indexes from access patterns. Use transactions for invariants and migrations that support safe rollout and rollback.
6. For asynchronous work, define retries, timeouts, dead-letter handling, idempotency keys, and observability.
7. Write tests at unit, integration, and contract levels. Include failure paths and concurrency cases.
8. Instrument structured logs, metrics, traces, and health checks without logging secrets or sensitive payloads.

## Review checklist
- Are contracts and failure modes explicit?
- Are authorization checks enforced server-side?
- Can retries create duplicate side effects?
- Are migrations backward-compatible during deployment?
- Are resource limits and timeouts configured?
- Can operators diagnose failures from telemetry?

Prefer the project's existing stack and conventions. Do not introduce infrastructure or dependencies without a concrete need.

Curated local skill inspired by the backend-development plugin from https://github.com/wshobson/agents. This is not a verbatim mirror of the upstream plugin.