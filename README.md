# take-away-monitoring-docker
Docker based monitoring VM with Graphite and Grafana

## Setup
### Ubuntu 14.04

	sudo mkdir /docker-data
	sudo chmod 777 /docker-data
	sudo apt-get update
	sudo apt-get upgrade
	sudo apt-get install git ntp
	sudo service ntp start
	sudo update-rc.d ntp start 20 2 3
	git clone https://github.com/tilmans/take-away-monitoring-docker.git
	cd take-away-monitoring-docker
	sudo mkdir /docker-data/elasticsearch
	sudo cp elasticsearch.yml /docker-data/elasticsearch/
	sudo sh install-ubuntu.sh
	sudo docker-compose up

### CentOS 7

	mkdir /docker-data
	chmod 777 /docker-data
	chcon -Rt svirt_sandbox_file_t /docker-data
	yum update
	yum install docker docker-registry git
	chkconfig docker on
	service docker start
	curl -L https://github.com/docker/compose/releases/download/1.1.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
	chmod +x /usr/local/bin/docker-compose
	git clone https://github.com/tilmans/take-away-monitoring-docker.git
	cd take-away-monitoring-docker
	mkdir /docker-data/elasticsearch
	chcon -Rt svirt_sandbox_file_t /docker-data/elasticsearch
	cp elasticsearch/elasticsearch.yml /docker-data/elasticsearch/
	docker-compose up

