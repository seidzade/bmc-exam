Vagrant.require_version ">=1.7.0"

Vagrant.configure(2) do |config|
	config.vm.box = "centos/7"
	config.ssh.insert_key = false
	instances_names = ["cns0", "mng0", "mng1", "node0", "node1"]

	instances_names.each do |name|
		config.vm.define name do |config|
			config.vm.network "private_network", type: "dhcp"
		end
	end

	groups = {
			"group-mngrs" => [
				"mng0",
				"mng1"
			],
			"group-cnss" => ["cns0"],
			"group-nodes" => [
				"node0",
				"node1",
			]
		}

	config.vm.provision "ansible" do |ansible|
		ansible.verbose = "v"
		ansible.groups = groups
		ansible.playbook = "playbook.yml"
	end
end
