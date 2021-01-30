Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/centos7"

  config.vm.hostname  = "devops1"
  
  config.vm.provider "virtualbox" do |vb|
    vb.customize [ "modifyvm", :id, "--memory", "1024", "--cpus", "1" ]
  end

  config.vm.network "private_network", ip:"192.168.2.102"

  config.vm.network "forwarded_port", guest:80, host:80
  config.vm.network "forwarded_port", guest:9100, host:9100
  config.vm.network "forwarded_port", guest:9200, host:9200
  config.vm.network "forwarded_port", guest:5601, host:5601
 
  
  


 
  # config.vm.provision "shell", path: "preinstall.sh"

end
