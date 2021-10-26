# Webapp Role: Webapp is a project made for ansible role training

An Webapp Role that installs one webapp instance of Linux, specially tailored for CentOS Distribution

## Requirements

This roles needs Docker Compose, requires Docker, Python Pip already be installed

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

The administrator who realize the deploy

    administrator: David

The Instance 1 variables, uses to create ressources of this specific webapp instance

    instance_1:
      name: GRETA
      port: 8080
      docker_name: webpp
      site_name: Webapp 
      title: My_website # name that should shown 


odoo parameter which permit user to manage database needs to be true when odoo DB doesn't exist    

    list_db: True


## Use with Ansible and `docker` Python library if doesn't install

Many users of this role wish to also use Ansible to then _build_ Docker images and manage Docker containers on the server where Docker is installed. In this case, you can easily add in the `docker` Python library using the `geerlingguy.pip` role:

```yaml
- hosts: rpi

  vars:
    pip_package: python3-pip
    pip_install_packages:
      - name: docker

  roles:
    - geerlingguy.pip
    - geerlingguy.docker_arm
```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: client
  become: true
  vars:
    pip_package: python3-pip
  vars_files:
    - files/secrets/credentials.yml
  roles:
    #- geerlingguy.pip
    #- geerlingguy.docker
    - odoo
```

## Author Information

This role was created in 2021 by [David JAMES](https://github.com/davijam/)
