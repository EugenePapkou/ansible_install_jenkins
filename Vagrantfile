Vagrant.configure("2") do |config|
  config.vm.define "webserver" do |webserver|
    webserver.vm.box = "sbeliakou/centos"
    webserver.vm.box_version = "7.5"  
    webserver.vm.hostname = "webserver"
    webserver.vm.network "private_network", ip: "192.168.1.6"
    webserver.vm.provider "virtualbox" do |vb|
      vb.name = "webserver"
      vb.memory = "1500"
    end
  end

  config.vm.define "appserver" do |appserver|
    appserver.vm.box = "sbeliakou/centos"
    appserver.vm.box_version = "7.5"  
    appserver.vm.hostname = "appserver"
    appserver.vm.network "private_network", ip: "192.168.1.7"
    appserver.vm.provider "virtualbox" do |vb|
      vb.name = "appserver"
      vb.memory = "1500"
    end
  end
end
