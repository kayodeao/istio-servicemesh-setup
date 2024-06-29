## Install from the cert-manager release manifest
All resources (the CustomResourceDefinitions and the cert-manager, cainjector and webhook components) are included in a single YAML manifest file:

Install all cert-manager components:
```
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.15.1/cert-manager.yaml
```
By default, cert-manager will be installed into the cert-manager namespace. It is possible to run cert-manager in a different namespace, although you'll need to make modifications to the deployment manifests.
