---
layout: default
title: Common Kubernetes Operations
parent: Doppler
grand_parent: Internal Documentation
nav_order: 1
---

# Common Kubernetes Operations

This guide covers common Kubernetes operations for the Doppler system.

## Pod Management

### Finding Pods

To find pods for a specific replication group:

```bash
kubectl get pods -n monitoring | grep <replication-group-name>
```

### Checking Pod Logs

To view logs for a specific pod:

```bash
kubectl logs -n monitoring <pod-name>
```

## Troubleshooting

### Pod Status Issues

1. Check pod status:
   ```bash
   kubectl describe pod -n monitoring <pod-name>
   ```

2. Check pod events:
   ```bash
   kubectl get events -n monitoring | grep <pod-name>
   ```

### Resource Issues

1. Check resource usage:
   ```bash
   kubectl top pod -n monitoring <pod-name>
   ```

2. Check node resources:
   ```bash
   kubectl describe node <node-name>
   ```

## Common Operations

### Restarting Pods

To restart a pod:

```bash
kubectl delete pod -n monitoring <pod-name>
```

### Scaling Deployments

To scale a deployment:

```bash
kubectl scale deployment -n monitoring <deployment-name> --replicas=<count>
```

## Best Practices

1. Always check pod logs before taking action
2. Use describe for detailed troubleshooting
3. Monitor resource usage regularly
4. Document any manual interventions