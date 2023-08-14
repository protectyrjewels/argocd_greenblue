# Blue-Green Deployment with Argo Rollouts

This repository showcases the implementation of a blue-green deployment strategy for deploying two instances of an application using Argo Rollouts, an advanced Kubernetes controller for managing application deployments.

Before running an example:

1. Install Argo Rollouts

- See the document [Getting Started](https://argoproj.github.io/argo-rollouts/getting-started/)

2. Install Kubectl Plugin

- See the document [Kubectl Plugin](https://argoproj.github.io/argo-rollouts/features/kubectl-plugin/)

To run an example:

1. Apply the manifests of one of the examples:

```bash
kustomize build . | kubectl apply -f -
```

2. Watch the rollout or experiment using the argo rollouts kubectl plugin:

```bash
kubectl argo rollouts get rollout <ROLLOUT-NAME> --watch
kubectl argo rollouts get experiment <EXPERIMENT-NAME> --watch
```

3. For rollouts, trigger an update by setting the image of a new color to run:
```bash
kubectl argo rollouts set image <ROLLOUT-NAME> "*=argoproj/rollouts-demo:yellow"
```

4. To access a nice looking dashboard, run:
```bash
kubectl argo rollouts dashboard
```
