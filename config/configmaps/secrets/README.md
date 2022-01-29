# k8s Secrets

It's important to remember:
1. Limit access to etcd (where Secrets are stored) to only admin users
2. Use SSL/TLS for etcd peer-to-peer communication
3. Manifest (YAML|JSON) files only base64 encode the secret 
    - **be careful**, it's trivial to: 
      ```
      echo Ym9ndXMgcHVibGljIGtleQo= | base64 --decode
      ```
4. Pods can access Secrets, so secure which users can create Pods. Role-based access control (RBAC) can be used.

---

### Create Secret generic --from-literal
The following command creates and stores a `Secret` securely in Kubernetes.
```
kubectl create secret generic my-secret --from-literal=pwd=my-passord
```

--- 

### Create Secret generic --from-file
The following command creates and stores a `Secret` given a file in Kubernetes.
```
kubectl create secret generic my-secret-from-file --from-file=ssh-privatekey=~/.ssh/id_rsa --from-file=ssh-publickey=~/.ssh/id_rsa.pub
```

---

### Create Secret tls --cert --key
The following command creates and stores a tls `Secret` given a cert & key file in Kubernetes.
```
kubectl create secret tls my-tls-secret --cert=~/certs/tls.cert --key=~/certs/tls.key
```

## Learn More
Learn more about encrypting secrets at rest here: https://kubernetes.io/docs/tasks/administer-cluster/encrypt-data/
