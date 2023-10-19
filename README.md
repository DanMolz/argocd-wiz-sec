# How to deploy Wiz Kubernetes Connector with ArgoCD

## Install ArgoCD to your kubernetes cluster via helm
```sh
helm repo add argo https://argoproj.github.io/argo-helm
helm install argocd --create-namespace --namespace argocd argo/argo-cd
```

## Create Wiz secrets
```sh
kubectl -n wiz-kubernetes-connector create secret generic wiz-kubernetes-connector \
  --from-literal=clientId=123456789 \
  --from-literal=clientToken=123456789
```

## Create the Wiz Kubernetes Application
```sh
git clone https://github.com/DanMolz/argocd-wiz-sec.git
kubectl apply -f prod/wiz-kubernetes-connector.yaml
```
