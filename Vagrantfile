# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"


$script = <<SCRIPT
sudo apt-get update
sudo apt-get install python-dev python-setuptools -y
sudo easy_install pip
sudo pip install ansible -U
cd /vagrant
ansible-playbook -i localhost, -c local raptor-playbook.yml
SCRIPT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |vb|
     vb.customize ["modifyvm", :id, "--memory", "2048"]
  end
 
  config.vm.provision :shell, :inline => $script

end
