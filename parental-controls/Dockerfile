# Parental-Controls
#
# Version 0.0.1

FROM ubuntu:14.04
MAINTAINER Paradrop Team <info@paradrop.io>

RUN apt-get update
RUN apt-get -y install iptables 
RUN apt-get -y install privoxy dansguardian
RUN sed -i 's/listen-address  localhost:8118/listen-address  127.0.0.1:8118/' /etc/privoxy/config
RUN sed -i 's/proxyport = 3128/proxyport = 8118/' /etc/dansguardian/dansguardian.conf
RUN sed -i 's/UNCONFIGURED - Please remove this line after configuration//' /etc/dansguardian/dansguardian.conf
RUN echo "hoofersailing.org" >> /etc/dansguardian/lists/bannedsitelist

RUN echo "iptables -A PREROUTING -t nat -i wlan0 -p tcp --dport 80 -j REDIRECT --to-port 8080" >> /usr/local/bin/cmd.sh
RUN echo "iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE" >> /usr/local/bin/cmd.sh
RUN echo "service privoxy force-reload" >> /usr/local/bin/cmd.sh
RUN echo "service dansguardian start" >> /usr/local/bin/cmd.sh
RUN echo "while true; do sleep 421; done" >> /usr/local/bin/cmd.sh

CMD ["/bin/bash","/usr/local/bin/cmd.sh"]
