# 06 — Authentication Selection

## Start with the identity requirement

| Requirement | Starting approach |
|---|---|
| Conventional web application | Secure server-side sessions |
| React SPA + API | Established identity provider with suitable OAuth 2.0 / OpenID Connect flow |
| Google/Microsoft login | OpenID Connect through the provider |
| Enterprise SSO | OIDC or SAML according to organizational standards |
| Service-to-service identity | Workload identity, OAuth access tokens, or mutual TLS where appropriate |
| Higher-risk accounts | MFA/passkeys plus secure recovery and session policy |

OAuth 2.0 is an authorization framework; OpenID Connect adds an identity layer.

## Sessions vs JWT access tokens

| Factor | Server-side session | JWT access token |
|---|---|---|
| State | Session stored server-side | Token carries claims and can be validated locally |
| Revocation | Session invalidation can be straightforward | Requires careful expiry, refresh, and revocation strategy |
| Scaling | Shared session store or suitable routing may be needed | Distributed validation is possible; key and policy management remain |
| Security | Cookie, CSRF, and session controls matter | Storage, transport, validation, and token theft risks matter |

JWT is not automatically safer or more scalable.

## Spring Security baseline

- Use Spring Security and a trusted identity provider where appropriate.
- Require HTTPS.
- Validate issuer, audience, signature, expiry, and required claims.
- Enforce authorization on every protected backend resource.
- Protect cookie-based sessions with appropriate cookie attributes and CSRF controls.
- Configure CORS narrowly; CORS is not authorization.
- Store secrets securely and rotate them.
- Apply least privilege to users, services, and database identities.
- Plan MFA, account recovery, rate limiting, and audit logging where appropriate.
- Never rely on hiding a React button to protect an API.

## Threat-model questions

- What data or action is sensitive?
- Who can access it, and at what scope?
- How are accounts recovered?
- How quickly must compromised access be revoked?
- What should be logged, and what must never be logged?
