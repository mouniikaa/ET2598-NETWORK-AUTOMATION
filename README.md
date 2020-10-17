# ET2598-NETWORK-AUTOMATION !!!



In this project we aim to implement a web service.

1) Here there is basic PHP line which is stored in index.php 
2) Webserver used was NGINX 
3) Assuming there is a load , we execute three NGINX servers initially and      require a HAproxy to load balance the servers.


The site consists of 5 hosts which are 
1)HAproxy
2)A (webserver)
3)B (webserver)
4)C (webserver)
5)Bastion 


TASK :-

The basic service is an Nginx web server, that only serves one simple PHP page. That page renders the hostname, IP, and port of the server running it. 

The service to expected to be a massive hit with our intended customers, so we cannot just run one web server. We need to run multiple web servers. Initially, we want to have three Nginx servers running on three different platforms. To make access simple, we want HAproxy to load balance between these three servers. 

Ansible-playbook, site.yaml, that deploys the HAproxy, and Nginx on appropriate existing hosts, i.e. the playbook does not need to launch any Virtual Machines.

The playbook is assumed to run -outside- the site, but -via- the Bastion host. Hence, you need to have an SSH config file that allows your host to use the Bastion host as a jump host, using an SSH key. Furthermore, the Bastion host also needs to have SSH access to all of the site-local hosts, using SSH keys, to avoid typing passwords all the time. The playbook should also do a rudimentary function test of the deployed application. That test is to send three requests to the public IP associated with HAproxy, and verify that all three hosts A, B, and C answers. 
