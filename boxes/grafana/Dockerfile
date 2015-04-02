# DOCKER-VERSION 0.4.0
from	ubuntu:14.04

env REFRESHED_AT 2014_03_30

run	echo 'deb http://us.archive.ubuntu.com/ubuntu/ precise universe' >> /etc/apt/sources.list
run	apt-get -y update

# Install required packages
run	apt-get -y install nginx-light wget

run wget http://grafanarel.s3.amazonaws.com/grafana-1.9.1.tar.gz
run tar -xvzf grafana-1.9.1.tar.gz
run mv grafana-1.9.1 www

# Add system service config
add	./nginx.conf /etc/nginx/nginx.conf
add ./config.js /www/config.js

# Nginx
expose	:80

ENTRYPOINT ["/usr/sbin/nginx","-g","daemon off;"]
