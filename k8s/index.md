# K8s handy commands

## Get Pods in a weird state

```shell
kubectl get pods --all-namespaces | grep -v -e "Completed" -e "Running"
```

## Port forward from a pod to a local port

```shell
kubectl port-forward -n dsp dsp-fpe-db-6458bf568-4v2fj 7200:7200
```
## Create a job from a cron job

```
kubectl create job dsp-pro-load-data-manual -n dsp --dry-run=client --from=cronjob/dsp-pro-load-data -o yaml > /Users/monika/dsp-pro-load-data-manual-job.yaml
```

## Copy from Pod to local

```
kubectl -n dsp cp ~/Downloads/<file-to-move> dsp-bathing-waters-db-<pod-id>:/fuseki/databases/ds_again.nq.gz -c dsp-bathing-waters-db`
```