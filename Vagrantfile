# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"

  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end

  config.vm.network "forwarded_port", guest: 5000, host: 5000

  config.vm.provision "ansible_local" do |ansible|
    ansible.extra_vars = {
      TESTNET: true,
      VAGRANT: true
    }
    ansible.playbook = "ansible/deploy.yml"
    ansible.verbose = "vvvv"
  end
end
