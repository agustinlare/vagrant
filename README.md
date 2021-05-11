# Vagrant

## Most used commands

```=bash
vagrant up
vagrant halt
vagrant ssh
vagrant provision
```

# Add Boxes 
[Boxes inventory](https://app.vagrantup.com/boxes/search)

`$ vagrant box add imagen --provider hyperv`

# Deafult provider Hyper-V (Powershell CLI)

`[Environment]::SetEnvironmentVariable("VAGRANT_DEFAULT_PROVIDER", "hyperv", "User")`


## Plugins

```=bash
vagrant plugin install vagrant-reload 
vagrant plugin install vagrant-git
vagrant plugin install vagrant-vbguest && vagrant vbguest
```

## Share folder

`co.vm.synced_folder "./", "/vagrant", owner: "vagrant", mount_options: ["dmode=775,fmode=600"]`

## Call scripts from file
```
SCRIPT_IFCONFIG = "../scripts/ifcfg-eth0.sh"
sc.vm.provision "shell", path: SCRIPT_IFCONFIG, privileged: true, args: "192.168.0.202"
```

## Otras boxes
* Raspberry: jriguera/rpibuilder-buster-10.2-i386