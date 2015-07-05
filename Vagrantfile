# -*- mode: ruby -*-
# vi: set ft=ruby :

box_name = "dry-docks"

Vagrant.configure(2) do |config|

  config.vm.define box_name do |box|
    box.vm.provider "virtualbox" do |v|
      v.name = box_name
    end

    box.vm.box = "ubuntu/trusty64"

    box.vm.network "private_network", type: "dhcp"

    box.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/playbook.yml"
      ansible.limit = "all"
    end

    box.vm.synced_folder "./", "/vagrant", type: "nfs"

  end

end
