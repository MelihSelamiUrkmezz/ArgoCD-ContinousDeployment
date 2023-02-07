v# ArgoCD

## What's the ArgoCD?

Argo CD is a declarative continuous delivery tool for Kubernetes applications. 
It uses the GitOps style to create and manage Kubernetes clusters. When any changes are made to the application configuration in Git, Argo CD will compare it with the configurations of the running application and notify users to bring the desired and live state into sync.

## How to setup ArgoCD your k8s cluster?

- kubectl create namespace argocd
- kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

## How to see this ArgoCD admin user's password?

- kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

## How to export argocd-server service?

kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'
