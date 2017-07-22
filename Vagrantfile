Vagrant.require_version ">= 1.5"

Vagrant.configure("2") do |config|

    config.vm.provider :virtualbox do |v|
        v.name = "default"
        v.customize [
            "modifyvm", :id,
            "--name", "default",
            "--memory", 1024,
            "--natdnshostresolver1", "on",
            "--cpus", 2,
        ]
    end

    config.vm.box = "ubuntu/trusty64"

    config.vm.network :private_network, ip: "192.168.1.99"
    config.ssh.forward_agent = true

    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "ansible/playbook.yml"
        ansible.inventory_path = "ansible/inventories/dev"
        ansible.limit = 'all'
    end

    # Files on your local machine
    config.vm.synced_folder "/Webdev/example", "/vagrant"
end
