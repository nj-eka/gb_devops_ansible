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
    vb.cpus = 1
    vb.qemu_use_session = false
  end

  config.vm.define "haproxy" do |haproxy|
    haproxy.vm.box = "generic/ubuntu2004"
    haproxy.vm.box_check_update = false
    haproxy.vm.hostname = "haproxy"
    haproxy.vm.network "private_network", ip: "10.10.10.3"
    config.vm.provision "file", source: "/home/set/Документы/geekbrains/keys/project.pub", destination: "/home/vagrant/.ssh/"
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
    config.vm.provision "file", source: "/home/set/Документы/geekbrains/keys/project.pub", destination: "/home/vagrant/.ssh/"
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
    config.vm.provision "file", source: "/home/set/Документы/geekbrains/keys/project.pub", destination: "/home/vagrant/.ssh/"
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
    config.vm.provision "file", source: "/home/set/Документы/geekbrains/keys/project.pub", destination: "/home/vagrant/.ssh/"
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
    config.vm.provision "file", source: "/home/set/Документы/geekbrains/keys/project.pub", destination: "/home/vagrant/.ssh/"
    monitoring.vm.provision "shell", inline: <<-SHELL
        chmod 600 /home/vagrant/.ssh/project.pub
        cat /home/vagrant/.ssh/project.pub >> /home/vagrant/.ssh/authorized_keys
    SHELL
  end
end

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "10.58.4.20"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount tehe folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "F:/DevOps", "/home/vagrant"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
