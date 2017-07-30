Vagrant.require_version ">=1.7.0"

Vagrant.configure(2) do |config|
	config.vm.box = "centos/7"
	config.ssh.insert_key = false
	instances_names = ["cns0", "mgr0", "mgr1", "node0", "node1"]

	instances_names.each do |name|
		config.vm.define name do |config|
			config.vm.network "private_network", type: "dhcp"
		end
	end

	groups = {
			"managers" => [
				"mgr0",
				"mgr1"
			],
			"consuls" => ["cns0"],
			"nodes" => [
				"node0",
				"node1",
			]
		}

	config.vm.provision "main", type: "ansible" do |ansible|
		ansible.verbose = "v"
		ansible.groups = groups
		ansible.playbook = "provision.yml"
	end
        config.vm.provision "app", type:"ansible" do |ansible|
                ansible.verbose = "v"
                ansible.groups = groups
                ansible.playbook = "install_app.yml"
        end
end
