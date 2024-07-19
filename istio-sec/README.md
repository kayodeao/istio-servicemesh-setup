## Verify policy enforcement, mtLS and authorization policy:

### Exec into  any of the Pod
Exec into the pod. Use the following command to access the pod:
```
kubectl exec -it <pod-name> -n <namespace> -c istio-proxy -- /bin/bash
```
```
 curl -o /dev/null -s -w "response_code: %{http_code}\n" http://<service>.<namespace>.svc.cluster.local:80
```
