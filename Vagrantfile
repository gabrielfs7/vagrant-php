Vagrant.require_version ">= 1.7.2"


# VM configuration
Vagrant.configure(2) do |config|
    config.vm.boot_timeout = 300

    # Public HashiCorp vagrant box (https://atlas.hashicorp.com/boxes/search)
    config.vm.box = "ubuntu/trusty64"
    config.vm.box_check_update = true

    # When calling vagrant halt
    config.vm.graceful_halt_timeout = 60

    config.vm.hostname = "vagrant.local"

    # Ip and port to vagrant access
    config.vm.network :private_network

    # Message after vagrant up
    config.vm.post_up_message = "Vagrant up successfully :)"

    # VM provider configuration
    config.vm.provider "virtualbox" do |vb|
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
    end

    # Config provisioners. Softwares that can be installed and configured when VM is created
    config.vm.provision "shell",
        inline: "echo Hello, World"

    # HTTP port forwarding
    # config.vm.forward_port 80, 8080
end