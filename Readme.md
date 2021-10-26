### Ansible project deployment example

Hosts preparation
> ssh-keygen -t rsa
> ssh-copy-id admin@<ip-address>
  
Modify ip in prod.yml
> vi prod.yml  

Run command to deploy 
> ansible-playbook -i prod.yml deploy.yml

#### Ansible documentation
https://docs.ansible.com/ansible/latest/
