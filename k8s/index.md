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

## change context

```
kubectx <context-nmae>
```

## Create a secret in kubernetes
```
echo -n "http://admin:<<password>>:8080/repositories/defra-aims-001/statements" | kubectl create secret generic aims-dsp -n dsp --dry-run=client --from-file=sparqlUpdateEndpoint=/dev/stdin -o yaml > secret2.yaml
```
## Given a sealed secret file, create a sealed secret
On test

```
cat auth-secret.yaml | kubeseal --controller-name=sealed-secrets --controller-namespace=kube-system --format yaml > sealed-secret.yaml
```
On live, note the difference in the name of the kubeseal controller
```
cat auth-secret.yaml | kubeseal --controller-name=sealed-secrets-controller --controller-namespace=kube-system --format yaml > sealed-secret.yaml
```
