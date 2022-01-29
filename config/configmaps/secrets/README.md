# k8s Secrets

It's important to remember:
1. Limit access to etcd (where Secrets are stored) to only admin users
2. Use SSL/TLS for etcd peer-to-peer communication
3. Manifest (YAML|JSON) files only base64 encode the secret
4. Pods can access Secrets, so secure which users can create Pods. Role-based access control (RBAC) can be used.

### Create Secret
The following command creates and stores a `Secret` securely in Kubernetes.
```
kubectl create secret generic my-secret --from-literal=pwd=my-passord
```

Learn more about encrypting secrets at rest here: https://kubernetes.io/docs/tasks/administer-cluster/encrypt-data/
