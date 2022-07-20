$script = <<-'SCRIPT'
sudo apt update
sudo apt-get install ansible -y
wget -P /tmp https://github.com/prometheus/node_exporter/releases/download/v1.3.1/node_exporter-1.3.1.linux-amd64.tar.gz --no-check-certificate
ansible-playbook /vagrant/provision/main_local.yml
SCRIPT

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu2004"
#  config.vbguest.auto_update = false
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.define "compose" do |compose|
    compose.vm.network "private_network", ip: "192.168.56.102"
    compose.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
    end
    compose.vm.hostname = "compose"
  end
  config.vm.provision "ansible-provision", type: "shell", inline: $script
#  config.vm.provision "COMPOSE", type:'ansible' do |ansible|
#    ansible.inventory_path = './provision/inventory'
#    ansible.playbook = './provision/main.yml'
#  end
end
