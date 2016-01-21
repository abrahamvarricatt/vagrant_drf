# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API version
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
	config.vm.box = "centos/7"
	config.vm.network "private_network", ip: "192.168.33.10"
	config.vm.network "forwarded_port", guest: 80, host: 8080
#	config.ssh.username = "root"
#	config.ssh.password = "vagrant"

	config.vm.provider "virtualbox" do |vb|
		vb.memory = "1024"
		vb.cpus = "2"
	end

	config.vm.provision "ansible" do |ansible|
		ansible.playbook = "site.yml"
		ansible.inventory_path = "hosts/dev"
		ansible.limit = "all"
		ansible.extra_vars = { ansible_ssh_user: 'vagrant' }
		ansible.sudo = true
		ansible.verbose = "vvvv"
	end
end


