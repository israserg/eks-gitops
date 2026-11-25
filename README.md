# eks-gitops

Desired state of the `arc-training` EKS cluster. Argo CD watches this repo.

- `root/`: one Argo CD `Application` per app. The root app (from Terraform in `eks-arc`) syncs this folder.
- `apps/demo/chart/`: Helm chart for the demo app. It is a **manual copy** of `chart/` in the
  `eks-demo-app` repo. When that chart changes, copy it here (`diff -r` shows drift).
  Which image runs is set in `root/demo.yaml` (`helm.valuesObject.image.tag`).

Deploy = commit. Roll back = `git revert`. Training only; contains no secrets.
