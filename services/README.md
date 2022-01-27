# Services

### Quick Tip for debugging services
Shell into a pod and test a URL. Add `-c [containerID]`
in cases where multiple containers are running in the Pod
```
kubectl exec [pod-name] -- curl -s http://podIP
```

Install and use curl (for example, when it's not available on an Alpine Linux container)
```
kubectl exec [pod-name] --stdin --tty -- sh
> apk add curl
> curl -s http://podIP
```

Display the pod yaml to check the assigned podIP

```
kubectl get pod [pod-name] -o yaml
```
at the end of the yaml you'll see something like:
```
  ...
  hostIP: 192.168.65.4
  phase: Running
  podIP: 10.1.0.74
  podIPs:
  - ip: 10.1.0.74
  qosClass: Guaranteed
  startTime: "2022-01-27T01:27:43Z"
```
you can use the podIP to access the pod from within the cluster.


