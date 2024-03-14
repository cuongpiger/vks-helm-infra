# Installation
```bash
CLUSTER_NAME=<put-your-cluster-name>
NAMESPACE=<put-your-namespace>

helm repo add vks-helm-infra https://cuongpiger.github.io/vks-helm-infra
helm repo update
helm install ${CLUSTER_NAME} vks-helm-infra/datastore -n ${NAMESPACE} --create-namespace
```

_(update later)_