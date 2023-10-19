# How to deploy Wiz Kuberentes Connector with ArgoCD

## Install ArgoCD to your kubernetes cluster via helm
```sh
helm repo add argo https://argoproj.github.io/argo-helm
helm install argocd --create-namespace --namespace argocd argo/argo-cd
```

## Create the Wiz Kubernetes Application
```sh
git clone https://github.com/DanMolz/argocd-wiz-sec.git
kubectl apply -f ~/prod/wiz-values.yaml
```
