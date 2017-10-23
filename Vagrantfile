# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "ubuntu/xenial64"
    ubuntu.vm.network "private_network", ip: "192.168.27.100"
    ubuntu.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
      vb.cpus = 2
    end
    ubuntu.vm.provision "shell", inline: "apt update && apt install -y nginx"
    ubuntu.vm.provision "shell", inline: "ln -s /vagrant /var/www/html/demo"
  end

  config.vm.define "ubuntu2" do |ubuntu2|
    ubuntu2.vm.box = "ubuntu/xenial64"
    ubuntu2.vm.network "private_network", ip: "192.168.27.101"
    ubuntu2.vm.provider "virtualbox" do |vb2|
      vb2.memory = 1024
      vb2.cpus = 1
    end
  end
end
