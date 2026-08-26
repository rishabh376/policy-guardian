# policy-guardian

> Regulated Product Teams coordinate rotate workload credentials for PCI workloads, so unsigned builds never reach staging.

**Domain:** devsecops | **Complexity:** intermediate | **Stack:** Go, OPA Gatekeeper, Vault, Trivy, Cosign, Falco

| | |
|---|---|
| Use case | Regulated Product Teams coordinate rotate workload credentials for PCI workloads, so unsigned builds never reach staging. |
| Pain point | Secret rotation depends on calendar reminders and late-night manual checks. |
| Success metric | Rotate leaked or stale credentials within 15 minutes without app downtime. |
| Cost | $0/mo on Cloudflare |

## Why this exists

Secret rotation depends on calendar reminders and late-night manual checks.. Regulated Product Teams coordinate rotate workload credentials for PCI workloads, so unsigned builds never reach staging.

> This service shifts security left with scans, signatures, and admission controls so teams can ship safely. For this implementation, the service is designed to remove the operational friction behind Regulated Product Teams coordinate rotate workload credentials for PCI workloads, so unsigned builds never reach staging..

## What this product does

This project ships a production-oriented service that exposes health, readiness, observability, and domain-specific endpoints for Regulated Product Teams coordinate rotate workload credentials for PCI workloads, so unsigned builds never reach staging.. The implementation is intended to be deployed behind Kubernetes with secure defaults, CI validation, and rollback-ready manifests.

## Quick start

```bash
docker build -t policy-guardian:local .
docker run -p 8080:8080 policy-guardian:local
curl http://localhost:8080/healthz
```

## Architecture

```
GitHub CI -> Container Registry -> Kubernetes -> Go -> Operators / SRE
```

See `docs/ARCHITECTURE.md`

## Infrastructure

Full spec: `terraform/INFRA_REQUIREMENTS.md`

TL;DR: K8s cluster, 2-10 pods HPA, $0 on Cloudflare

## Docs

- `docs/ARCHITECTURE.md` - components, tradeoffs
- `docs/DESIGN_DISCUSSION.md` - how we decided to build this
- `docs/DEPLOYMENT.md` - GitOps, rollback
- `docs/SECURITY.md` - threat model
- `docs/TROUBLESHOOTING.md` - 3am runbook
- `terraform/INFRA_REQUIREMENTS.md` - **infra: CPU/RAM/storage/cost**

Interview prep: `interview/`
