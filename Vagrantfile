# -*- mode: ruby -*-
# vi: set ft=ruby :
# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

ENV['VAGRANT_DEFAULT_PROVIDER'] = 'libvirt'
Vagrant.configure("2") do |config|
  config.vm.provider :libvirt do |vb|
    vb.driver = "qemu"
    vb.memory = 2048
    vb.cpus = 2
    vb.qemu_use_session = false
  end

  config.vm.define "haproxy" do |haproxy|
    haproxy.vm.box = "generic/ubuntu2004"
    haproxy.vm.box_check_update = false
    haproxy.vm.hostname = "haproxy"
    haproxy.vm.network "private_network", ip: "10.10.10.3"
    config.vm.provision "file", source: "/home/jn/gb/keys/project.pub", destination: "/home/vagrant/.ssh/"
    haproxy.vm.provision "shell", inline: <<-SHELL
        chmod 600 /home/vagrant/.ssh/project.pub
        cat /home/vagrant/.ssh/project.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
    config.vm.define "wordpress1" do |wordpress1|
    wordpress1.vm.box = "generic/ubuntu2004"
    wordpress1.vm.box_check_update = false
    wordpress1.vm.hostname = "wordpress1"
    wordpress1.vm.network "private_network", ip: "10.10.10.4"
    config.vm.provision "file", source: "/home/jn/gb/keys/project.pub", destination: "/home/vagrant/.ssh/"
    wordpress1.vm.provision "shell", inline: <<-SHELL
        chmod 600 /home/vagrant/.ssh/project.pub
        cat /home/vagrant/.ssh/project.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
    config.vm.define "wordpress2" do |wordpress2|
    wordpress2.vm.box = "generic/ubuntu2004"
    wordpress2.vm.box_check_update = false
    wordpress2.vm.hostname = "wordpress2"
    wordpress2.vm.network "private_network", ip: "10.10.10.5"
    config.vm.provision "file", source: "/home/jn/gb/keys/project.pub", destination: "/home/vagrant/.ssh/"
    wordpress2.vm.provision "shell", inline: <<-SHELL
        chmod 600 /home/vagrant/.ssh/project.pub
        cat /home/vagrant/.ssh/project.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
    config.vm.define "database" do |database|
    database.vm.box = "generic/ubuntu2004"
    database.vm.box_check_update = false
    database.vm.hostname = "database"
    database.vm.network "private_network", ip: "10.10.10.6"
    config.vm.provision "file", source: "/home/jn/gb/keys/project.pub", destination: "/home/vagrant/.ssh/"
    database.vm.provision "shell", inline: <<-SHELL
        chmod 600 /home/vagrant/.ssh/project.pub
        cat /home/vagrant/.ssh/project.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
    config.vm.define "monitoring" do |monitoring|
    monitoring.vm.box = "generic/ubuntu2004"
    monitoring.vm.box_check_update = false
    monitoring.vm.hostname = "monitoring"
    monitoring.vm.network "private_network", ip: "10.10.10.7"
    config.vm.provision "file", source: "/home/jn/gb/keys/project.pub", destination: "/home/vagrant/.ssh/"
    monitoring.vm.provision "shell", inline: <<-SHELL
        chmod 600 /home/vagrant/.ssh/project.pub
        cat /home/vagrant/.ssh/project.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
end
