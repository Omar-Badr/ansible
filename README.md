# Using ansible to automate the creation of a multi-container Web-app.

- Initialize an ubuntu VM using `Vagrant`
- Provision the VM using `Ansible` to create the following environment:
- create `nginx` web server `Docker` container
- create `MySQL` database `Docker` container
- deploy 2 instances of the following project: `https://github.com/ealeksandrov/NodeAPI` inside a `Docker` container
- create an `haproxy` docker container to load balance the 2 instances created above
- The deployment should allow a request to pass through: `nginx` -> `haproxy` -> `node`

#Enviroment

OS= Ubuntu 14.04.5 LTS (GNU/Linux 3.13.0-137-generic x86_64) 

Vagrant Version= 2.0.1

Virtualbox Version= 4.3.36_Ubuntur105129

Ansible Version= ansible 2.4.2.0

Python Version= 2.7.6

#Guest VM
Guest VM= ubuntu/trusty64
Guest VM IP= 192.168.33.27
Guest VM Name= hostVM

#Containers:

mysql name= mysql_cont 

mysql IP= 172.1.1.100

nginx name= nginx_cont

nginx IP= 172.1.1.101

nginx port mapping= 8080:80

node rest api 1 name= my_node_rest_api_con_1

node rest api 1 IP= 172.1.1.102

node rest api 2 name= my_node_rest_api_con_2

node rest api 2 IP= 172.1.1.103

haproxy name= my_haproxy_con

haproxy IP= 172.1.1.104

