# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "kalilinux/rolling"
    config.vm.box_version = "2022.3.2"
    
    config.ssh.forward_agent="true"
    config.ssh.forward_x11="true"
  
    # config.vm.network "forwarded_port", guest: 8834, host: 8834
  
    config.vm.synced_folder "./data", "/vagrant", SharedFoldersEnableSymlinksCreate: false
  
    config.vbguest.auto_update = false
    config.vbguest.no_remote = true
    
    # VirtualBox specific settings
    config.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.cpus = 4
      vb.memory = "8192"
    end
  
    # Provision the machine with a shell script
    #config.vm.provision "shell", inline: <<-SHELL
    #  apt-get update
    #  apt-get install -y crowbar
    #SHELL
  end