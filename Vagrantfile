# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 2
  end


  config.vm.define "k3shead" do |k3shead|
  k3shead.vm.box = "ubuntu/xenial64"
  #k3shead.vm.provision :shell, path: "web.sh" 
  k3shead.vm.network "forwarded_port", guest: 80, host: 8080
  k3shead.vm.network "private_network", ip: "192.168.33.10"
  k3shead.vm.network "public_network", bridge: "en1: Intel(R) 82579LM Gigabit Network Connection"
  end

  config.vm.define "k3snode" do |k3snode|
  k3snode.vm.box = "ubuntu/xenial64"
  #k3snode.vm.provision :shell, path: "web.sh" 
  k3snode.vm.network "forwarded_port", guest: 80, host: 8081
  k3snode.vm.network "private_network", ip: "192.168.33.11"
  k3snode.vm.network "public_network", bridge: "en1: Intel(R) 82579LM Gigabit Network Connection"
  end

  config.vm.define "file" do |file|
  file.vm.box = "ubuntu/xenial64"
  #file.vm.provision :shell, path: "web.sh" 
  file.vm.network "forwarded_port", guest: 80, host: 8082
  file.vm.network "private_network", ip: "192.168.33.12"
  file.vm.network "public_network", bridge: "en1: Intel(R) 82579LM Gigabit Network Connection"
  end




  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
