# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API version
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
	config.vm.box = "ubuntu/trusty64"
	config.vm.network "private_network", ip: "192.168.33.10"
	config.vm.network "forwarded_port", guest: 80, host: 8080
#	config.ssh.username = "root"
#	config.ssh.password = "vagrant"

	config.vm.provider "virtualbox" do |vb|
		vb.memory = "1024"
		vb.cpus = "2"
	end

	config.vm.provision "ansible" do |ansible|
		ansible.playbook = "vagrant.yml"
		ansible.host_key_checking = false
		ansible.verbose = "v"
	end
end


