sudo mkdir $HOME/.kube
sudo cp /etc/rancher/k3s/k3s.yaml $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
sudo usermod -aG docker vagrant

helm repo add stable https://kubernetes-charts.storage.googleapis.com
helm repo update
helm install metallb stable/metallb --namespace kube-system \
  --set configInline.address-pools[0].name=default \
  --set configInline.address-pools[0].protocol=layer2 \
  --set configInline.address-pools[0].addresses[0]=192.168.20.1-192.168.20.250

  cat /etc/docker/daemon.json
{
  "insecure-registries" : ["192.168.200.6:30002"]
}