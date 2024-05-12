# Technical-task

## Local Testing

A Vagrantfile is provided that provision a 3 nodes cluster using Vagrant (Virtualbox as provider). To use it:

```bash
vagrant up
```

By default, each node is given 2 cores and 2GB of RAM and runs Ubuntu 20.04. You can customize these settings by editing the `Vagrantfile`.


# install ArgoCD in k8s
- `kubectl create namespace argocd`
- `kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml` 

# access ArgoCD UI
- `kubectl get svc -n argocd`
- `kubectl port-forward svc/argocd-server 8080:443 -n argocd` 

# login with admin user and below token (as in documentation):
- `kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo`

# deploying a dummy Helm chart to ArgoCD, follow these steps:

Inside the repository, create a directory named `helmcharts`.
- `helm create helmcharts`

 
