![Kubernetes](https://img.shields.io/badge/kubernetes-%23326ce5.svg?style=for-the-badge&logo=kubernetes&logoColor=white) ![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=Helm&labelColor=0F1689) ![Go](https://img.shields.io/badge/go-%2300ADD8.svg?style=for-the-badge&logo=go&logoColor=white) ![Github Pages](https://img.shields.io/badge/github%20pages-121013?style=for-the-badge&logo=github&logoColor=white) ![Shell Script](https://img.shields.io/badge/shell_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white)
# VngCloud CAPI Controller Manager
![dev-staging-env](https://badgen.net/badge/DEV-STAGING/environment/blue?icon=github)
<hr>

# 1. Installation
## 1.1. Prerequisites
- Helm 3.0+
- `KUBECONFIG` environment variable pointing to the `.kubeconfig` file with access to your Kubernetes cluster.

## 1.2. Install `vngcloud-capi-controller-manager` on Kubernetes
- Following the below steps to install `vngcloud-capi-controller-manager` on your Kubernetes cluster:
  - **Step 1**: Add the `vks-helm-infra` Helm repository:
    ```
    helm repo add vks-helm-infra https://cuongpiger.github.io/vks-helm-infra
    helm repo update
    ```

  - **Step 2**: Install `vngcloud-capi-controller-manager`:
    ```
    helm install vngcloud-capi-controller-manager vks-helm-infra/vngcloud-capi-controller-manager --replace \
      --namespace kube-system \
      --set cloudConfig.global.clientID=<PUT_YOUR_CLIENT_ID> \
      --set cloudConfig.global.clientSecret=<PUT_YOUR_CLIENT_SECRET> \
      --set cluster.clusterID=<PUT_YOUR_CLUSTER_ALIAS_NAME>
    ```

## 1.3. Uninstall `vngcloud-capi-controller-manager` from Kubernetes
- Following the below steps to uninstall `vngcloud-capi-controller-manager` from your Kubernetes cluster:
  ```
  helm uninstall vngcloud-capi-controller-manager --namespace kube-system
  ```

## 1.4. Upgrade `vngcloud-capi-controller-manager` on Kubernetes
- Following the below steps to upgrade `vngcloud-capi-controller-manager` on your Kubernetes cluster:
  ```bash
  helm upgrade vngcloud-capi-controller-manager vks-helm-infra/vngcloud-capi-controller-manager --replace \
    --namespace kube-system \
    --set cloudConfig.global.clientID=<PUT_YOUR_CLIENT_ID> \
    --set cloudConfig.global.clientSecret=<PUT_YOUR_CLIENT_SECRET> \
    --set cluster.clusterID=<PUT_YOUR_CLUSTER_ALIAS_NAME>
  ```
