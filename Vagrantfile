$hosts_script = <<SCRIPT
apt-get update
apt-get -q -y install python
git clone https://github.com/guidolarrain1981/docker-mysql-master-slave.git
SCRIPT

$hosts_script_2 = <<SCRIPT
echo "#######################################"
echo "#######################################"
echo "###### Initiate Replication ###########"
echo "#######################################"
echo "#######################################"
cd /home/vagrant/docker-mysql-master-slave/
./build.sh
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.hostname = "mysql"
  config.vm.define "mysql"
  config.vm.provider :virtualbox do |v|
    v.name = "mysql"
    v.customize ["modifyvm", :id, "--memory", "1024"]
  end
  config.vm.network :private_network, ip: "10.211.55.116"
  config.vm.provision :shell, :inline => $hosts_script

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "ansible/site.yml"
    ansible.inventory_path = "ansible/hosts"
  end

  config.vm.provision :shell, :inline => $hosts_script_2

end
