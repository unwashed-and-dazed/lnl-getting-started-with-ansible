# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # CentOS
  config.vm.define "centos" do |centos|
    centos.vm.hostname = "centos.avenuecode"
    centos.vm.box = "centos/7"
    centos.vm.box_check_update = false
    centos.vm.network "private_network", ip: "192.168.123.20"

    centos.vm.provider "virtualbox" do |v|
        v.gui = false
        v.name = "AC - CentOS 7"
        v.memory = "600"
        v.cpus = "1"
    end
  end
  # End centos

  # Debian
  config.vm.define "debian" do |debian|
    debian.vm.hostname = "debian.avenuecode"
    debian.vm.box = "debian/stretch64"
    debian.vm.box_check_update = false
    debian.vm.network "private_network", ip: "192.168.123.30"

    debian.vm.provider "virtualbox" do |y|
        y.gui = false
        y.name = "AC - Debian 9"
        y.memory = "600"
        y.cpus = "1"
    end

  end
  # End Debian

end
