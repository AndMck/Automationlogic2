# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'

Vagrant.configure("2") do |config|
  
    # Create Initial VM
    config.vm.define "ans" do |ans|
      ans.vm.box = "puppetlabs/ubuntu-14.04-64-nocm"
      ans.vm.hostname = "web1"
      ans.vm.network "private_network", ip: "192.168.20.10"
      ans.vm.network "forwarded_port", guest: 80, host: 8080
    
          # Run Ansible from the Vagrant VM
      config.vm.provision "shell", path: "install_nginx.sh" 
      
    end
    
end