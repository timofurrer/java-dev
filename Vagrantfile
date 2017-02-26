# Get command which is used with vagrant command
VAGRANT_COMMAND = ARGV[0]
def provisioned?(vm_name='default', provider='virtualbox')
    File.exist?(".vagrant/machines/#{vm_name}/#{provider}/action_provision")
end

Vagrant.configure(2) do |config|
    config.vm.box = "ubuntu/xenial64"
    if provisioned?
        config.vm.synced_folder "../", "/home/batman/hslu", owner: "batman", group: "batman"
    end
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
