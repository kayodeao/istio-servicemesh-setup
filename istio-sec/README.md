## Verify policy enforcement, mtLS and authorization policy:

### Verify mTLS
Open an interactive shell in the frontendservice pod. Use the following command to access the pod:
```
kubectl exec -it <pod-name> -n <namespace> -c istio-proxy -- /bin/bash
```
test connectivity
```
 curl -o /dev/null -s -w "response_code: %{http_code}\n" http://<service>.<namespace>.svc.cluster.local:80
```

### verify Authorization policy

Creat a new namespace  and deploy a debug pod. We will make HTTP requests to various services and endpoints within the mesh. By observing the responses (allowed or denied), we can confirm whether the authorization policies are correctly enforced.


Open an interactive shell in the debug pod:
```
kubectl exec -it debug-pod -n debug-namespace -- /bin/sh
```
test connectivity
```
 curl -o /dev/null -s -w "response_code: %{http_code}\n" http://<service>.<namespace>.svc.cluster.local:<port>
```
