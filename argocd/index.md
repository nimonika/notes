# Running a pipeline and syncing in Argocd

  1. Pipelines can be found [here](https://dev.azure.com/agrimetricsdsp/DSPApps/_build)
  2. Once you push a new app image, run the pipeline manually
  3. Get the tag of the newly built image - it is the one shown on the pipeline, ignore the last letter/number
  4. In argocd descriptors, replace the value of the image tag in `values-live.yaml` and `values-test.yaml`
