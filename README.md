### Overview of Project 13

**Elk-Stack**

The goal of this project was to utilize the Azure platform to build a secure network that uses load balancing to manage housed - virtual web servers, that communicate with a DVWA database. 

The configuration places the web servers behind a firewall, with only one point of access, referred to as a jumpbox.

A jumpbox adds an additional layer of security between the virtual servers and the public internet by using access rules to control inbound / outbound traffic. 

Load balancing is important because it allows resources to be monitored and shared, more adequately between the web servers.  

Please review the configuration details of each machine below.

**Name	Function	IP Address	Operating System**

* JumpBox	Gateway	10.0.0.4	Linux(ubtntu 18.04)
* Web-1	Server	10.1.0.5	Linux(ubtntu 18.04)
* Web-2	Server	10.1.0.7	Linux(ubtntu 18.04)
* Web-3	Server	10.1.0.8	Linux(ubtntu 18.04)

**Access Policies**

The machines on the internal network are not exposed to the public Internet.
Only the DVWA machine can accept connections from the Internet. Any user can currently access the DVWA machine when it is running.
Machines within the network can only be accessed by whitelisted users. The current whitelisted users public IP is being used, and allowed over only certain ports that our ELK stack is running.

**Elk setup**

Ansible ([ansible config file](https://github.com/framarkarus/Elk-Stack---Project-13/wiki/Ansible)) was used to automate the configuration of the ELK machine, which allowed for quick and accurate deployment. 
The Ansible playbook used the following for completion
* docker.io
* python-pip
* docker module using pip
* Increases the virtual memory of our ELK box
Downloads and launches the sebp/elk container over ports 5601, 9200, and 5044.
The following commands must be used to access the containers
- ssh azadmin@JumpBox(Public IP)
- sudo docker container list -a (locate your ansible container)
- sudo docker start container (name of the container)
- sudo docker attach container (name of the container)

[Azure network topology](https://github.com/framarkarus/Elk-Stack---Project-13/wiki/Azure-network-topology)
