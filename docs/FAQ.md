# FAQ - policy-guardian

**Q: What problem does this actually solve?**
A: Regulated Product Teams coordinate rotate workload credentials for PCI workloads, so unsigned builds never reach staging.

Pain point: Secret rotation depends on calendar reminders and late-night manual checks.

**Q: Free to run?**
A: Yep. Cloudflare - $0/mo. See `terraform/INFRA_REQUIREMENTS.md`

**Q: Production ready?**
A: Yes - SLOs, security hardening, DR runbook, Helm, Terraform, monitoring.

**Q: Stack?**
A: Go, OPA Gatekeeper, Vault, Trivy, Cosign, Falco

**Q: What infra do I need?**
A: `terraform/INFRA_REQUIREMENTS.md` has the full breakdown - CPU/RAM/storage/network/cost.
