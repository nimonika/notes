# K8s handy commands

## Get Pods in a weird state

```
kubectl get pods --all-namespaces | grep -v -e "Completed" -e "Running"
```
