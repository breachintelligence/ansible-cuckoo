[![Build Status](https://travis-ci.org/breachintelligence/ansible-cuckoo.svg?branch=master)](https://travis-ci.org/breachintelligence/ansible-cuckoo)

# ansible-cuckoo
Ansible Playbook for installing and configuring [Cuckoo Sandbox](http://www.cuckoosandbox.org/)

**This is not production code yet.**

This playbook was inspired by [ezetze's ansible-cuckoo](https://github.com/ezeteze/ansible-cuckoo) with changes to support Cuckoo Sandbox 2.0.

The playbook is tested on **Ubuntu 14.04 x64**.  **CentOS 7 w/ SELinux Enforcing** support coming soon.

Uses Ansible playbook structure with three distinct roles:

-	**Cuckoo**: This role downloads cuckoo version 2.0-rc1 from official github repository and installs required dependencies. 
-	**Virtualbox**: This role adds the official virtualbox ppa repository for Ubuntu and installs virtualbox. 
-	**Web**: This role configures  nginx  web server and gunicorn  in order to serve the cuckoo web application.

To install cuckoo on a local Ubuntu 14.04 LTS virtual machine clone this repo and issue the following commands:

    sudo apt-add-repository ppa:ansible/ansible && apt-get update
    sudo apt-get –y install git ansible 
    git clone https://github.com/breachintelligence/ansible-cuckoo
    cd ansible-cuckoo
    sudo ansible-playbook -i hosts site.yml --connection=local

----------
