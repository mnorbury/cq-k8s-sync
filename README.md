# cq-k8s-sync

Configuration files for a CloudQuery sync from xkcd to a neon database using ArgoCD to reconcile against a Kind cluster.

## Setup

1. Create the kind cluster

```bash
kind create cluster --name cq-k8s-sync
```

2. Install ArgoCD

```bash
brew install argocd
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

3. Install KubeSeal 

```bash
brew install kubeseal
```

4. Download the kubeseal manifest from [github](https://github.com/bitnami-labs/sealed-secrets/releases)

```bash
kubectl apply -f ~/Downloads/controller.yaml
```

5. Create the sync namespace

```bash
kubectl create ns sync
```

