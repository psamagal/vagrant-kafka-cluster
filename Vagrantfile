Vagrant.configure("2") do |config|
   config.vm.box = "centos/6"
   config.vm.provision :shell, path: "./scripts/install.sh"


  config.vm.define "zookeeper" do |subconfig|
    subconfig.vm.network "public_network", bridge: "enp4s0", ip: "192.168.1.201"
    subconfig.vm.provision "ansible" do |ansible|
        ansible.playbook = "provision/zookeeper.yml"
    end
  end

  config.vm.define "kafka01" do |subconfig|
    subconfig.vm.network "public_network", bridge: "enp4s0", ip: "192.168.1.202"
    subconfig.vm.provision "ansible" do |ansible|
        ansible.playbook = "provision/kafka.yml"
    end
  end

  config.vm.define "kafka02" do |subconfig|
    subconfig.vm.network "public_network", bridge: "enp4s0", ip: "192.168.1.203"
    subconfig.vm.provision "ansible" do |ansible|
        ansible.playbook = "provision/kafka.yml"
    end
  end

  config.vm.define "kafkamanager" do |subconfig|
    subconfig.vm.network "public_network", bridge: "enp4s0", ip: "192.168.1.204"
    subconfig.vm.provision "ansible" do |ansible|
        ansible.playbook = "provision/kafkamanager.yml"
    end
  end
end 