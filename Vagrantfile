# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "http://yum.oracle.com/boxes/oraclelinux/ol73/ol73.box"
  
  config.vm.box_check_update = false
  
  # change memory size
  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.name = "oracle12c-vagrant"
  end

  # Oracle port forwarding
  config.vm.network "forwarded_port", guest: 1521, host: 1521
  config.vm.network "forwarded_port", guest: 5500, host: 5500

  # Provision everything on the first run
  config.vm.provision "shell", path: "scripts/install.sh"

end
