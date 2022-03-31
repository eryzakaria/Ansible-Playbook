Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/focal64"
    config.vm.provider "virtualbox" do |vb|

      vb.cpus = 1
      vb.memory = "512"
      vb.linked_clone = true
    end

    config.vm.define "nginx1" do |nginx1|
      nginx1.vm.network :private_network, ip: "10.10.10.20"
    end
    config.vm.define "nginx2" do |nginx2|
      nginx2.vm.network :private_network, ip: "10.10.10.21"
    end

    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y curl 
    SHELL
  end
  