# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.network "private_network", ip: "192.168.33.11"
  config.vm.hostname = "iiif-server-vagrant"
  config.vm.synced_folder "data/", "/vagrant/data", create: true

  config.vm.provider "virtualbox" do |vb|
    vb.name = "iipimage-server-vagrant"
    vb.memory = "2048"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "iiif-server.yml"
    ansible.inventory_path = "hosts"
    ansible.limit = "iiif-server-vagrant"
    ansible.verbose = 'v'

    ansible.extra_vars = { ansible_ssh_user: 'vagrant'}
  end

end
