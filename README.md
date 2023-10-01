- Criar o cluster K3D

    <!-- k3d cluster create -p "8081:30080@server:0" -p "80:31080@server:0" -p "443:32080@server:0" --servers 1 --agents 1 -->
    k3d cluster create -c ../k3d_config_cluster.yaml

- Pegar credencial para acessar o ArgoCD

    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

<!-- - Acessar página ArgoCD

    kubectl port-forward svc/argocd-server -n argocd 8080:443 -->