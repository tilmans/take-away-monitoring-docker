# Dockerfile for statsd
#
# VERSION               0.1
# DOCKER-VERSION        0.4.0

from    ubuntu:14.04
run     apt-get -y update
run     apt-get -y install wget git python nodejs npm
run     git clone git://github.com/etsy/statsd.git statsd

add     ./config.js ./statsd/config.js

expose  8125/udp
expose  8126/tcp

cmd     nodejs /statsd/stats.js /statsd/config.js
