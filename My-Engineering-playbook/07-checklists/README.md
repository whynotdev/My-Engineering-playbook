# 07 — Engineering Checklists

## Design review

- [ ] Requirements, constraints, and quality attributes documented
- [ ] Alternatives and trade-offs recorded
- [ ] Data ownership and transaction boundaries clear
- [ ] Security and privacy reviewed
- [ ] Cost and operational ownership understood
- [ ] Failure modes and recovery documented

## Pull request

- [ ] Code is focused and readable
- [ ] Tests cover expected behavior and edge cases
- [ ] Validation and error handling are appropriate
- [ ] No secrets or sensitive data are committed
- [ ] Authorization is enforced server-side
- [ ] Database migrations are included when needed
- [ ] Logs avoid secrets and unnecessary personal data
- [ ] Documentation is updated

## Production readiness

- [ ] CI/CD and rollback path tested
- [ ] Environment configuration and secrets are secure
- [ ] Health checks, logs, metrics, and alerts exist
- [ ] Backups are configured and restoration tested
- [ ] Capacity and connection limits reviewed
- [ ] Dependency/security scanning is in place
- [ ] Incident owner and escalation path identified
- [ ] Cost alerts and budget assumptions reviewed

## Handover

- [ ] Repository and deployment ownership transferred
- [ ] Architecture and ADRs documented
- [ ] Environment setup instructions work
- [ ] Operational runbook and recovery steps included
- [ ] Known issues and limitations disclosed
- [ ] Third-party accounts, domains, and billing ownership clarified
