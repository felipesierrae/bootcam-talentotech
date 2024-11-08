./pacman-install.sh`

Alternatively, run `./pacman-uninstall.sh keeppvc`. This will delete all objects except for the pacman namespace and the persistent volume claim. You can use this to demonstrate persistence of the MongoDB data by installing, playing a game and recording a high score, then unininstalling with the `keeppvc` argument. You can then run the installation again and the high score will persist.

## Arquitectura

* Namespace
* Deployment
  * MongoDB Pod
    * DB 
    * PVC
  * Pac-Man Pod
    * Nodej
* RBAC
* Secret
* Service
================
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

helm install kube-prometheus-stack prometheus-community/kube-prometheus-stack

helm upgrade --install \
  -f https://raw.githubusercontent.com/cloudnative-pg/cloudnative-pg/main/docs/src/samples/monitoring/kube-stack-config.yaml \
  prometheus-community \
  prometheus-community/kube-prometheus-stack