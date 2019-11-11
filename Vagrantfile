# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.box_check_update = false
  config.vm.define "hw1" do |hw1|
      hw1.vm.hostname = "ansible.hw1"
      hw1.vm.network "private_network", type: "dhcp"
      hw1.vm.provider "virtualbox" do |vb|
          vb.gui = false
          vb.memory = 1024
          vb.name = "hw1"
      end
  end
  config.vm.define "hw2" do |hw2|
      hw2.vm.hostname = "ansible.hw2"
      hw2.vm.network "private_network", type: "dhcp"
      hw2.vm.provider "virtualbox" do |vb|
          vb.gui = false
          vb.memory = 1024
          vb.name = "hw2"
      end
  end
end
