# K8s handy commands

## Get Pods in a weird state

```
k8s get pods --all-namespaces | grep -v -e "Completed" -e "Running"
```
