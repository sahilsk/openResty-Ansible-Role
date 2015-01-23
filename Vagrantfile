# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty32"

  # config.vm.network "forwarded_port", guest: 80, host: 8080

   config.vm.network "public_network"

  # config.vm.synced_folder "../data", "/vagrant_data"

   config.vm.provider "virtualbox" do |vb|
     vb.memory = "512"
   end

  Vagrant.configure("2") do |config|
    config.vm.provision "shell", inline: "echo Hello"

    config.vm.define "workstation" do |wk|
      wk.vm.network "private_network", ip: "192.168.33.10"
      wk.vm.synced_folder "../ansibleOrchestration", "/vagrant_data"
    end

    config.vm.define "loadbalancer" do |lb|
      config.vm.network "private_network", ip: "192.168.33.11"
    end
  end


end
