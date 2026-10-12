# 05 — Cloud Selection

## Principle

Choose the cloud that fits the client's approved platform, identity system, region, compliance, skills, and total cost. Do not select by brand alone.

## High-level comparison

| Factor | AWS | Azure | Google Cloud |
|---|---|---|---|
| General-purpose infrastructure | Broad service portfolio | Broad service portfolio | Broad service portfolio |
| Microsoft enterprise ecosystem | Integrates with Microsoft products | Often a natural fit | Integrates with Microsoft products |
| Analytics and data | Broad options | Broad options | Strong analytics ecosystem |
| Existing organization standards | Often decisive | Often decisive | Often decisive |
| Cost predictability | Requires usage modeling | Requires usage modeling | Requires usage modeling |

This is a high-level orientation, not a universal ranking. All three can host Java, React, and PostgreSQL solutions in multiple ways.

## Checklist

1. Is a cloud already mandated by the client?
2. Are identity, networking, security, and monitoring standardized?
3. Which regions satisfy latency and data-residency needs?
4. Estimate compute, database, storage, backup, egress, and support costs.
5. Does the team have operational expertise?
6. What are the service limits and recovery options?
7. How difficult would migration be?
8. Are proprietary managed services worth the potential lock-in?

## Cost model

Estimate a normal month, peak month, and recovery/failover scenario. Include network egress, logs, backup retention, managed database minimums, and engineering time. Verify current prices with provider calculators before committing.

## Practical rule

For a client project, approved cloud standards and the ability to operate the solution usually matter more than small differences between providers.
