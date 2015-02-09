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
    config.vm.network :forwarded_port, guest: 80, host: 8080
    config.vm.network :forwarded_port, guest: 443, host: 8443
    config.vm.network :forwarded_port, guest: 3306, host: 3307
    config.vm.network :private_network, ip: "192.168.10.10"

    # Message after vagrant up
    config.vm.post_up_message = "Vagrant up successfully :)"

    # VM provider configuration
    config.vm.provider "virtualbox" do |vb|
        # Don't boot with headless mode
        vb.gui = false

        # Show screen on Virtualbox
        # vb.gui = true

        # Ram Memory
        vb.customize ["modifyvm", :id, "--cpuexecutioncap", "50"]
        vb.customize ["modifyvm", :id, "--memory", "1024"]
        vb.customize ["modifyvm", :id, "--ioapic", "on"]
        vb.customize ["modifyvm", :id, "--cpus", "2"]
    end

    # Config provisioners. Softwares that can be installed and configured when VM is created
    config.vm.provision "shell",
        inline: "echo Hello, World"
end