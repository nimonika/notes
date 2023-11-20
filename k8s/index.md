# K8s handy commands

## Get Pods in a weird state

```
kubectl get pods --all-namespaces | grep -v -e "Completed" -e "Running"
```
## Port forward from a pod to a local port

```
kubectl port-forward -n dsp dsp-fpe-db-6458bf568-4v2fj 7200:7200
```