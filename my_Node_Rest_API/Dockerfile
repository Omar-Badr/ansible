
FROM ubuntu:14.04
MAINTAINER Omar Badr <omar.ehab.badr@gmail.com>
COPY onstart.sh /usr/bin/onstart.sh
RUN sudo apt-get update && \
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6 && \
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5 && \
    sudo apt-get install apt-transport-https -y && \
    echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.6 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list && \
    sudo apt-get update && \
    sudo apt-get install git npm -y && \
    sudo git clone https://github.com/ealeksandrov/NodeAPI.git
WORKDIR "/NodeAPI"
RUN sudo apt-get install node nodejs -y && \
    sudo apt-get install mongodb -y && \
    sudo apt-get install mongodb-org -y 
RUN sudo mkdir -p /data/db && \
    sudo service mongodb start && \
    sudo npm install  && \
    sudo nodejs generateData.js
RUN chmod +x /usr/bin/onstart.sh

EXPOSE 80 443 1337 27017
CMD ["/usr/bin/onstart.sh"]

