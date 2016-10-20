# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  ## if vagrant-vbguest is installed stop auto updating virtualbox guest add-on update
  if defined? VagrantVbguest
    config.vbguest.auto_update = false
  end

  ## Base box
  config.vm.box = "ubuntu/trusty64"

  ## Network settings
  config.vm.network "private_network", ip: "192.168.33.10"

  ## Synced directories
  # config.vm.synced_folder "../data", "/vagrant_data"

  ## Provider settings
  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "512"
  end

  ## Provison settings
  config.vm.provision :ansible_local do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end

end
