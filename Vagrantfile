# Get command which is used with vagrant command
VAGRANT_COMMAND = ARGV[0]

Vagrant.configure(2) do |config|
    config.vm.box = "ubuntu/xenial64"
    config.vm.synced_folder "../", "/home/batman/hslu", owner: "batman", group: "batman"
    config.ssh.forward_x11 = true

    config.vm.provider "virtualbox" do |vb|
        vb.gui = false
        vb.memory = "4096"
    end

    config.vm.provision "ansible" do |ansible|
        ansible.playbook = "ansible/java-dev.yml"
        ansible.verbose = true
    end

    if VAGRANT_COMMAND == "ssh"
        config.ssh.username = "batman"
    end
end
