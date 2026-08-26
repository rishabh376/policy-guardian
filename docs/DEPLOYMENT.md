# Deployment - policy-guardian

**Use case:** Regulated Product Teams coordinate rotate workload credentials for PCI workloads, so unsigned builds never reach staging.

## Infra requirements
→ `terraform/INFRA_REQUIREMENTS.md` - CPU/RAM/storage/network/cost breakdown

## GitOps
Flux watches `main` and reconciles changes automatically.

## Rollback
```
./scripts/rollback.sh
kubectl rollout undo deploy/policy-guardian -n policy-guardian
```
Usually < 30 sec.

## Cost
Cloudflare - $0/mo

The focus is supply-chain hardening: SBOMs, Cosign signatures, and policy enforcement across build and deploy.
