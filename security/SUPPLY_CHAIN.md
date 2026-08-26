# Supply Chain Security - policy-guardian

Regulated Product Teams coordinate rotate workload credentials for PCI workloads, so unsigned builds never reach staging.

## Controls
- Trivy filesystem and image scans fail HIGH/CRITICAL findings before deploy.
- Cosign signs images in CI and Kyverno verifies signatures at admission.
- SBOM is generated in SPDX format and attached to the release artifact.
- OPA/Gatekeeper denies privileged pods and root containers.
- Vault or External Secrets handles runtime secrets; nothing sensitive is committed.

## Stack
Go, OPA Gatekeeper, Vault, Trivy, Cosign, Falco

## Interview Angle
Talk about where the gate sits: developer PR, CI scan, registry signature, Kubernetes admission, and runtime detection.
