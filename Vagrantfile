
Vagrant.configure("2") do |config|



	config.vm.provider "virtualbox" do |v|
		v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
		v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
	end

	
	config.vm.define "web" do |web|
		web.vm.box = "ubuntu/xenial64"
		# creating a virtual machine ubuntu
		web.vm.network "private_network", ip: "192.160.10.110"
#		web.hostsupdater.aliases = ["development.local"]
		web.vm.synced_folder "app", "/home/ubuntu/app"
		web.vm.provision "shell", path: "mongoDB/app/provision.sh"
	end
	
	
	config.vm.define "db" do |db|	
		db.vm.box = "ubuntu/xenial64"
		db.vm.network "private_network", ip: "192.160.10.150"
		db.vm.synced_folder "mongoDB/db", "/home/ubuntu/environment"
		db.vm.provision "shell", path: "mongoDB/db/provision.sh", privileged: false
	end


end
