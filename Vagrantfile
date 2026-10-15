Vagrant.configure("2") do |config|
    config.vm.box = "bento/ubuntu-22.04"
    config.vm.hostname = "ubuntu-server"

    config.vm.provider "virtualbox" do |vb|
        vb.name = "ubuntu-2204-server"
        vb.cpus = 2
        vb.memory = 2048
    end
end
