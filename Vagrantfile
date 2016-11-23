# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_DEFAULT_PROVIDER'] = 'virtualbox'

Vagrant.configure("2") do |config|
  
    # Create Initial VM
    config.vm.define "web1" do |web1|
      web1.vm.box = "puppetlabs/ubuntu-14.04-64-nocm"
      web1.vm.hostname = "web1"
      web1.vm.network "private_network", ip: "192.168.20.10"
      web1.vm.network "forwarded_port", guest: 80, host: 8080, id: "nginx"
    end
          # Run Ansible from the Vagrant VM
      config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end
    
end