# take-away-monitoring-docker
Docker based monitoring VM with Graphite and Grafana

## Setup
### Ubuntu 14.04

	sudo apt-get update
	sudo apt-get upgrade
	sudo apt-get install git
	git clone https://github.com/tilmans/take-away-monitoring-docker.git
	cd take-away-monitoring-docker
	sudo sh install-ubuntu.sh
	sudo docker-compose up

### CentOS 7
#### Make directory accessible:

	chcon -Rt svirt_sandbox_file_t /root/take-away-monitoring-docker/elasticsearch
	chcon -Rt svirt_sandbox_file_t /root/take-away-monitoring-docker/graphite

#### Adjust volume pathes in docker-compose

