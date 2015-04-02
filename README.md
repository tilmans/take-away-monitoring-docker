# take-away-monitoring-docker
Docker based monitoring VM with Graphite and Grafana

## Setup
### Make directory accessible:

	chcon -Rt svirt_sandbox_file_t /root/take-away-monitoring-docker/elasticsearch
	chcon -Rt svirt_sandbox_file_t /root/take-away-monitoring-docker/graphite

### Adjust volume pathes in docker-compose

