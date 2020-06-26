Vagrant.configure("2") do |config|
  config.vm.box = "bento/centos-7.4"
  config.vbguest.auto_update = false

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 4
  end   

  config.vm.define "master" do |master|
    master.vm.hostname = "master"
    master.vm.network "private_network", ip: "192.168.33.10"
  end
  
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "docker.yml"
    ansible.verbose = false
  end
  
end