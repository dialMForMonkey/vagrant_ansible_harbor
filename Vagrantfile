# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.

  config.vm.provider "virtualbox" do |v|
    v.memory = 2144
    v.cpus = 8
  end
  config.vm.define "fedora-harbor" do |fedora|
    fedora.vm.box = "fedora/34-cloud-base"
    fedora.vm.box_version = "34.20210423.0"
    fedora.vm.hostname = "cobaia-fedora-harbor"
    fedora.vm.network "private_network", ip: "192.168.1.2", hostname: true
    fedora.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbooks-ansible/harbor.yml"
    end
  end

  
end
