# Viewing Kubernetes Logs

### Logs for a pod
To view the logs for a pod:
```
kubectl logs [pod-name]
```

### Logs for a container
To view the logs for a specific container.
```
kubectl logs [pod-name] -c [container-name]
```

### Logs for a previously running pod
If the pod is not currently running but you'd 
like to inspect the logs, for example to see 
why it was killed.
```
kubectl logs -p [pod-name]
```

### Stream a pod's logs
To follow a pod's logs use the following command:
```
kubectl logs -f [pod-name]
```

