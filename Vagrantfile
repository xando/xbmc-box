# -*- mode: ruby -*-
# vi: set ft=ruby :

BOX_URL = "http://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

DEVELOPMENT_IP = "10.0.0.10"

Vagrant.configure("2") do |config|

  config.vm.boot_timeout = 3000
  config.vm.box_url = BOX_URL

  config.vm.box = "Ubuntu14.04-64"
  config.vm.network :private_network, ip: DEVELOPMENT_IP

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/deploy.yaml"
    ansible.inventory_path = "ansible/inventory.ini"
    ansible.verbose = "vvvv"
    ansible.host_key_checking = false
  end
  
end
