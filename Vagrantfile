# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT
mkdir /docker-data
chmod 777 /docker-data
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install -y git
git clone https://github.com/tilmans/take-away-monitoring-docker.git
cd take-away-monitoring-docker
mkdir /docker-data/elasticsearch
cp elasticsearch/elasticsearch.yml /docker-data/elasticsearch/
sudo sh install-ubuntu.sh
sudo docker-compose up
SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.provision "shell", inline: $script
end
