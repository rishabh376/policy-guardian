# Security - policy-guardian

What we do:
- Trivy scan in CI - blocks HIGH/CRITICAL
- Cosign sign images
- Non-root UID 10001, readOnlyRootFilesystem
- NetworkPolicy default-deny
- RBAC least-privilege
- Secrets via External Secrets / Vault (not in git)
- Dependabot + CodeQL on

Threat model: Secret rotation depends on calendar reminders and late-night manual checks.

The focus is supply-chain hardening: SBOMs, Cosign signatures, and policy enforcement across build and deploy.
