# -*- mode: ruby -*-
# vi: set ft=ruby :

#SERÁ GERADO PELO SELENIUM_PROC

VAGRANT_FILE_VERSION = 2

Vagrant.configure(VAGRANT_FILE_VERSION) do |config|

  config.vm.box        = 'ebrc/centos-7-64-puppet'

  config.ssh.username  = 'vagrant'
  config.ssh.password  = 'vagrant'
  config.ssh.insert_key = 'true'

  config.vm.provider :virtualbox do |virtualbox|
    virtualbox.customize ["modifyvm", :id, "--cpus", "2"]
    virtualbox.customize ["modifyvm", :id, "--memory", "3096"]
  end

  config.vm.define :selenium_puppetserver do |selenium_puppetserver|
	  selenium_puppetserver.vm.network "private_network", ip: "192.168.70.200"
	  #selenium_nexus.vm.network "forwarded_port", guest:8081, host: 8081
  end

  config.vm.provision "puppet" do |puppet|
  	puppet.environment_path = "environments"
  	puppet.environment 	= "development"
 	  puppet.module_path      = "puppet/modules"
  end
end
