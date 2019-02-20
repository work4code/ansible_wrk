Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
    v.cpus = 1
  end
  config.vm.define "ansible" do |ans|
    ans.vm.box = "centos/7"
    ans.vm.network "private_network", ip: "192.168.56.2"
    ans.vm.hostname = "ans"
  end

  config.vm.define "node1" do |nd1|
    nd1.vm.box = "centos/7"
    nd1.vm.network "private_network", ip: "192.168.56.3"
    nd1.vm.hostname = "nd1"
  end 
   
  config.vm.define "node2" do |nd2|
    nd2.vm.box = "centos/7"
    nd2.vm.network "private_network", ip: "192.168.56.4"
    nd2.vm.hostname = "nd2"
 
  end  
   
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "/opt/roles/vagrant.yml"
  
  end
end
