# homelab

brew install flux

## Flux config

source .keys

flux bootstrap github \
 --kubeconfig=../config/admin.conf \
 --owner=$GITHUB_USER \
 --repository=homelab \
 --path="kubernetes-cluster/lab" \
 --personal

flux get kustomizations --kubeconfig=../config/admin.conf

kubectl -n default get deployments,services --kubeconfig=../config/admin.conf
