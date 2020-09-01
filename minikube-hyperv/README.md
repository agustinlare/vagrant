# MINIKUBE

Provisionado para pruebas de reemplazo de docker-swarm en l003

## Vagrant

Provisionamiento local (pc AGUSTIN-L) de un minikube

## Helm Operator install

`kubectl apply -f https://raw.githubusercontent.com/fluxcd/helm-operator/1.1.0/deploy/crds.yaml`
`kubectl create ns flux`

`helm repo add fluxcd https://charts.fluxcd.io`

```bash
helm repo add stable https://kubernetes-charts.storage.googleapis.com
helm repo update
helm repo add gyfnexus http://nexus-legacy.gyf.com/repository/helm-hosted/
helm upgrade -i helm-operator fluxcd/helm-operator \
    --namespace flux \
    --set helm.versions=v3
```

## HelmRelease

```bash
cat <<EOF | kubectl apply -f ->>
apiVersion: helm.fluxcd.io/v1
kind: HelmRelease
metadata:
  name: adintar17
  namespace: default
spec:
  chart:
    repository: http://nexus-legacy.gyf.com/repository/helm-hosted/
    name: react-netcore-adintar17-bundle-uala-prod
    version: 1.7.31
EOF
```
