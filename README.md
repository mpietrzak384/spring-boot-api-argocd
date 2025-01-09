# spring-boot-api-argocd

This is an example of an argocd ApplicationSet:
- defines two sources:
  - one for retrieving the chart from this repository
  - second for retrieving values to supply the chart with
- uses ListGenerator in order to deploy apps in two environments
- uses helm to deploy the application
- used chart is defined in `chart/` directory
- values are defined in [sprint-boot-api-values](https://github.com/mpietrzak384/spring-boot-api-values) repository

## Usage

### Prerequisites

- k8s cluster
- argocd installed on the cluster - [ArgoCD: Getting Started](https://argo-cd.readthedocs.io/en/latest/getting_started/) . 
- kubectl

### Running

From root directory of this repo:

```shell
kubectl apply -f argocd/project.yaml
kubectl apply -f argocd/applicationset.yaml
```

Above commands should create an ArgoCD project and ApplicationSet which is responsible for deploying the app in two environments to targets: `spring-boot-api-dev`, `spring-boot-api-prd`