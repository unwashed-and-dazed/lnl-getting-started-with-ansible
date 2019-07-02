# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Ansible
  config.vm.define "ansible" do |ansible|
    ansible.vm.hostname = "ansible.avenuecode"
    ansible.vm.box = "centos/7"
    ansible.vm.box_check_update = false
    ansible.vm.network "private_network", ip: "192.168.123.10"

    ansible.vm.provision "shell", inline: <<-SHELL
      yum update -y
      yum install epel-release -y && yum install screen net-tools vim htop -y
    SHELL

    ansible.vm.provider "virtualbox" do |a|
        a.gui = false
        a.name = "AC - Ansible Runner"
        a.memory = "600"
        a.cpus = "1"
    end
  end
  # End Ansible

  # CentOS
  config.vm.define "centos" do |centos|
    centos.vm.hostname = "centos.avenuecode"
    centos.vm.box = "centos/7"
    centos.vm.box_check_update = false
    centos.vm.network "forwarded_port", guest: 80, host: 9090
    centos.vm.network "private_network", ip: "192.168.123.20"

    centos.vm.provision "shell", inline: <<-SHELL
      yum update -y
      yum install epel-release -y && yum install screen net-tools vim htop -y
    SHELL

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
    debian.vm.network "forwarded_port", guest: 3306, host: 9091
    debian.vm.network "private_network", ip: "192.168.123.30"

    debian.vm.provision "shell", inline: <<-SHELL
      apt update && apt upgrade -y
      apt install screen net-tools htop vim -y
    SHELL

    debian.vm.provider "virtualbox" do |y|
        y.gui = false
        y.name = "AC - Debian 9"
        y.memory = "600"
        y.cpus = "1"
    end

  end
  # End Debian

end
