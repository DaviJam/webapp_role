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
      project_name: Webapp 
      html_title: My_website # name that should shown 


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
    - davidjam.webapp_role
```

## Author Information

This role was created in 2021 by [David JAMES](https://github.com/davijam/)
