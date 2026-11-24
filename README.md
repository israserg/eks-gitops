# eks-gitops

Desired state of the `arc-training` EKS cluster. Argo CD watches this repo.

- `root/`: one Argo CD `Application` per app. The root app (from Terraform in `eks-arc`) syncs this folder.
- `apps/<name>/`: Kustomize manifests for each app.

Deploy = commit. Roll back = `git revert`. Training only; contains no secrets.
