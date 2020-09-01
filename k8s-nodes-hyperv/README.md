# Vagrant Draft

## Add boxes
https://app.vagrantup.com/boxes/search

`$ vagrant box add imagen --provider hyperv`

## Enviroment setup

`$ vagrant init`

Reemplazar la imagen base, ejemplo:

```
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/trusty64"
end
```

Deafult provider Hyper-V: `[Environment]::SetEnvironmentVariable("VAGRANT_DEFAULT_PROVIDER", "hyperv", "User")`

Start VM: `$ vagrant up --provider hyperv`

Destroy all VM's: `$ vagrant destroy --force`

Vagrant Plugin install: `$ vagrant plugin install vagrant-reload` `$ vagrant plugin install vagrant-git`

sudo mkdir $HOME/.kube
sudo cp /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
