## Verify policy enforcement, mtLS and authorization policy:

### Exec into the Pod
Exec into the pod. Use the following command to access the pod:
```
kubectl exec -it <pod-name> -n <namespace> -c istio-proxy -- /bin/bash
```
