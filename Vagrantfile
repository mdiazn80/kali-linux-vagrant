# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    config.vm.box = "kalilinux/rolling"
    config.vm.box_version = "2022.3.2"
    
    config.ssh.forward_agent="true"
    config.ssh.forward_x11="true"
  
    # config.vm.network "forwarded_port", guest: 8834, host: 8834
  
    config.vm.synced_folder "./data", "/vagrant"
  
    config.vbguest.auto_update = false
    config.vbguest.no_remote = true
    
    # VirtualBox specific settings
    config.vm.provider "virtualbox" do |vb|
      vb.default_nic_type = "82540EM"
      vb.gui = false
      vb.cpus = 4
      vb.memory = "8192"
      vb.customize ["modifyvm", :id, "--usb", "on"]
      vb.customize ['usbfilter', 'add', '0', '--target', :id, '--name', 'ALFA', '--vendorid', '0x148f', '--productid', '0x3070']
    end
  
    # Provision the machine with a shell script
    #config.vm.provision "shell", inline: <<-SHELL
    #  apt-get update
    #  apt-get install -y crowbar
    #SHELL
  end