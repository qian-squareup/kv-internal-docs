---
layout: default
title: Redis Node Down
parent: Incident Response
grand_parent: Runbooks
nav_order: 1
---

## Confirm Redis Node Status

There could be a variety of reasons why we’re not getting monitoring metrics for a given replication group.   For example

- Replication group decommissioned
- Permission issues in the monitoring agent

Confirm that the cluster is [healthy](https://www.notion.so/Working-with-Elasticache-1bdbe35268388002b01bc3a2e47ead65?pvs=21) before proceeding

### If the replication group no longer exists

Attempt to [remove](https://www.notion.so/Working-With-Etre-1bdbe35268388042972cca3c6b562087?pvs=21) the corresponding Etre entities.   Doppler should detect the change and remove the monitor pod for the replication group.   You can verify the pod is removed by following instructions [here](/kv-internal-docs/docs/internal_docs/doppler/common-kube-operations.html#finding-pods) and confirming 0 return values.

### If the replication group still exists

Check the monitoring pod logs following instructions [here](/kv-internal-docs/docs/internal_docs/doppler/common-kube-operations.html#checking-pod-logs). If you see errors related to permissions such as

> redis.exceptions.AuthenticationError: invalid username-password pair or user is disabled
> 

Following instructions [here](https://www.notion.so/Working-with-Elasticache-1bdbe35268388002b01bc3a2e47ead65?pvs=21) to fix the permissions