Vagrant.configure("2") do |config|
  config.vm.define "web" do |web|
    web.vm.box = "centos/7"
    web.vm.hostname = 'web'
    #web.vm.box_url = "centos/7"

    web.vm.network :private_network, ip: "10.9.8.10"
    #web.vm.network :forwarded_port, guest: 22, host: 10122, id: "ssh" ## uncomment if ssh access issue in port forwarding
    #web.vm.network :"forwarded_port", guest: 8080, host: 8080 ## port forward example
    web.vm.network "public_network"

    web.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 512]
      # v.customize ["modifyvm", :id, "--name", "web"]  ## uncomment to set the name in virtualbox
    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "centos/7"
    db.vm.hostname = 'db'
    #db.vm.box_url = "centos/7"

    db.vm.network :private_network, ip: "10.9.8.11"
    #db.vm.network :forwarded_port, guest: 22, host: 10222, id: "ssh" ## uncomment if ssh access issue in port forwarding
    #db.vm.network :"forwarded_port", guest: 8080, host: 8080 ## port forward example
    db.vm.network "public_network"


    db.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 512]
      #v.customize ["modifyvm", :id, "--name", "db"] ## uncomment to set the name in virtualbox
    end
  end

end
