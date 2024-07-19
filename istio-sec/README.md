# Introduction

To confirm whether the security policies are correctly enforced, we will deploy a debug pod. A debug pod is a Kubernetes pod specifically deployed for the purpose of troubleshooting and debugging issues within a Kubernetes cluster. These pods are typically lightweight and equipped with minimal tools necessary to diagnose and resolve problems, such as connectivity issues, configuration errors, or security policy verifications.

## Verify policy enforcement, mtLS and authorization policy:

### Verify mTLS
deploy the debug pod in the default namespace and open an interactive shell in the debug pod. Use the following command to access the pod:
```
kubectl exec -it <pod-name> -n <namespace> -c istio-proxy -- /bin/bash
```
test connectivity to the frontend service
```
 curl -o /dev/null -s -w "response_code: %{http_code}\n" http://frontend.default.svc.cluster.local:80
```

### verify Authorization policy

Creat a new namespace  and deploy the debug pod. We will make HTTP requests to various services and endpoints within the mesh. By observing the responses (allowed or denied), we can confirm whether the authorization policies are correctly enforced.


Open an interactive shell in the debug pod:
```
kubectl exec -it debug-pod -n debug-namespace -- /bin/sh
```
test connectivity
```
 curl -o /dev/null -s -w "response_code: %{http_code}\n" http://<service>.<namespace>.svc.cluster.local:<port>
```
