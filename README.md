- Criar o cluster K3D

    k3d cluster create -p "8081:30080@server:0" -p "8080:30081@server:0" --servers 1 --agents 1

- Pegar credencial para acessar o ArgoCD

    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d