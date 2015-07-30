# Parental-Controls
#
# Version 0.0.1

FROM ubuntu:14.04
MAINTAINER Paradrop Team <info@paradrop.io>

RUN apt-get update
RUN apt-get -y install iptables 

RUN echo "iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE" >> /usr/local/bin/cmd.sh
RUN echo "while true; do sleep 421; done" >> /usr/local/bin/cmd.sh

CMD ["/bin/bash","/usr/local/bin/cmd.sh"]
