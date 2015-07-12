# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.hostname = "omeka"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "omeka"
    vb.memory = "2048"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "omeka.yml"
    ansible.inventory_path = "hosts"
    ansible.limit = "omeka"
    ansible.verbose = 'v'

    ansible.extra_vars = { ansible_ssh_user: 'vagrant'}
  end

end
