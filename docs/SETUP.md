# Setup - policy-guardian

Regulated Product Teams coordinate rotate workload credentials for PCI workloads, so unsigned builds never reach staging.

1. **Infra first**: `cd terraform && terraform init && terraform apply`
2. `kubectl apply -k k8s/ -n policy-guardian`
3. `kubectl port-forward svc/policy-guardian 8080:80 -n policy-guardian`
4. `curl localhost:8080/healthz`

Env vars: `PORT=8080`, `LOG_LEVEL=info`

Runtime detection and telemetry let us prove the security controls are actually working in prod.
