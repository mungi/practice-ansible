# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "controller" do |config|
    config.vm.box = "centos/7"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "controller"
      vb.cpus = 2
      vb.memory = 2048
    end
    config.vm.hostname = "controller"
    config.vm.network "private_network", ip: "192.168.56.100"
  end

  config.vm.define "host1" do |config|
    config.vm.box = "centos/7"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "host1"
      vb.cpus = 1
      vb.memory = 1024
    end
    config.vm.hostname = "host1"
    config.vm.network "private_network", ip: "192.168.56.101"
  end

  config.vm.define "host2" do |config|
    config.vm.box = "centos/7"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "host2"
      vb.cpus = 1
      vb.memory = 1024
    end
    config.vm.hostname = "host2"
    config.vm.network "private_network", ip: "192.168.56.102"
  end

  # Hostmanager plugin
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = true

  # Enable SSH Password Authentication
  config.vm.provision "shell", inline: <<-SHELL
    sed -i 's/ChallengeResponseAuthentication no/ChallengeResponseAuthentication yes/g' /etc/ssh/sshd_config
    sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
    systemctl restart sshd
  SHELL
end
