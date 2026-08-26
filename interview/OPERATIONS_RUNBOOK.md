# Operations Runbook - policy-guardian

Regulated Product Teams coordinate rotate workload credentials for PCI workloads, so unsigned builds never reach staging.

**On-call? Read this first.**

## Deploy
```
kubectl apply -k k8s/ -n policy-guardian
kubectl rollout status deploy/policy-guardian -n policy-guardian
```

## Rollback (when things go red)
```
./scripts/rollback.sh
# usually < 30sec
```

## Scale up NOW
```
kubectl scale deploy/policy-guardian --replicas=10 -n policy-guardian
```

## Logs
```
kubectl logs -l app=policy-guardian -n policy-guardian -f --tail=200
```

## Crashloop?
```
kubectl describe pod -l app=policy-guardian -n policy-guardian
kubectl logs <pod> --previous -n policy-guardian
```
90% of the time: missing env var in ConfigMap.

## Metrics
`curl localhost:8080/metrics` or Grafana dashboard in `monitoring/`

## DR / Failover
See `docs/DISASTER_RECOVERY.md` - RTO 15m

We actually tested this. 11 min.
