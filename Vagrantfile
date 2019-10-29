# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "ubuntu" do |ubuntu|
    ubuntu.vm.box = "ubuntu/bionic64"
    ubuntu.vm.network :private_network, ip: "192.168.27.100"
    ubuntu.vm.provider :virtualbox do |vb|
      vb.memory = 1024
    	vb.cpus = 2
    end
    ubuntu.vm.provision :shell, :inline => "apt-get update && apt-get install -y nginx"
    ubuntu.vm.provision :shell, :inline => "ln -s /vagrant /var/www/html/demo"
  end

  config.vm.define "debian" do |debian|
    debian.vm.box = "debian/jessie64"
    debian.vm.network :private_network, ip: "192.168.27.101"
    debian.vm.provider :virtualbox do |vb|
      vb.memory = 1024
      vb.cpus = 1
    end
    debian.vm.provision :shell, :inline => "apt-get update && apt-get install -y nginx"
    debian.vm.provision :shell, :inline => "ln -s /vagrant /var/www/html/demo"
  end
end
