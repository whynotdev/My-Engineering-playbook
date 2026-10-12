# 01 — Technology Selection

## Purpose

Choose technologies based on business fit, team capability, delivery speed, security, operations, and total cost—not popularity.

## Default stack

For a typical business web application, use this as a starting point:

- **Frontend:** React + TypeScript
- **Backend:** Java + Spring Boot
- **Database:** PostgreSQL
- **API:** REST/JSON
- **Build:** Maven or Gradle, following team conventions
- **Version control:** Git + GitHub
- **CI/CD:** GitHub Actions or the organization-approved system
- **Deployment:** managed application/container hosting where practical
- **Authentication:** established identity provider integrated with Spring Security

This stack is a default, not a requirement. Existing client standards, team expertise, compliance, and integration needs can outweigh it.

## Weighted decision matrix

Rate each candidate from 1 (poor) to 5 (excellent). Calculate `sum(rating × weight) / 100`.

| Criterion | Weight | Questions |
|---|---:|---|
| Functional fit | 20% | Does it meet the actual requirements? |
| Delivery speed | 15% | How quickly can a reliable release ship? |
| Total cost | 15% | What are build, hosting, support, and migration costs? |
| Security/compliance | 15% | Can required controls be implemented and operated? |
| Maintainability | 15% | Can the team debug, test, upgrade, and support it? |
| Scalability | 10% | Can it meet the expected workload and growth? |
| Team expertise | 10% | Does the team know it; can we hire for it? |

A weighted score never overrides a mandatory requirement. Reject options that fail a required security, legal, or functional constraint.

## Quick mapping

| Requirement | Starting option | Caveat |
|---|---|---|
| Standard business web app | React + Spring Boot + PostgreSQL | Confirm team skills and existing standards |
| SEO-focused public pages | Evaluate Next.js / server rendering | Depends on content and SEO needs |
| Relational transactions | PostgreSQL | Model transaction boundaries carefully |
| Enterprise SSO | OIDC/SAML identity provider | Follow organizational identity standards |
| Background work | Worker or managed queue | Add durability/retries if required |
| Full-text search | PostgreSQL search initially; specialist search if needed | Benchmark real queries |
| Low operational capacity | Managed services | Review plan limits, portability, and total price |

## Budget and delivery profiles

- **Prototype:** minimal components, fast feedback, no unnecessary infrastructure.
- **MVP:** modular monolith, managed database if affordable, automated tests and deployment.
- **Growing product:** add observability, optimize measured bottlenecks, introduce cache/queue only where justified.
- **Enterprise:** design around identity, compliance, availability, recovery, integration, and ownership requirements.
- **High scale:** define workload and SLOs first; use selective partitioning, replicas, queues, or services when evidence justifies them.

## Common mistakes

- Choosing a technology before clarifying the problem.
- Scoring scalability highly without defining expected workload.
- Ignoring migration, operations, and staff time.
- Adopting multiple data stores without distinct requirements.
- Treating a free tier as a production reliability strategy.

## Decision checklist

- [ ] Requirements and constraints documented
- [ ] Viable alternatives compared
- [ ] Build and operating cost considered
- [ ] Security and compliance reviewed
- [ ] Team ownership established
- [ ] Validation and revisit criteria defined
