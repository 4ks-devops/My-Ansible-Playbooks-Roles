![GitHub](https://img.shields.io/badge/license-GPL--3.0-orange?style=plastic) ![GitHub](https://img.shields.io/badge/Python-2.7+-green?style=plastic) ![GitHub](https://img.shields.io/badge/Ansible-2.9+-blue?style=plastic) 

# My Ansible Playbooks and Roles
A Work-in-Progress (WIP), with more Playbooks and Roles adding regularly.  
  
## Ansible Tips and Tricks
Refer to [My Ansible Tips and Tricks](https://gist.github.com/d3athkai/3b1c6becc41d79f45332f238791ceb3d).  
  
# Recommended Ansible Settings
In `/etc/ansible/ansible.cfg`, under `[defaults]`, add:  
`interpreter_python=/usr/bin/python3`
  
## Playbooks
| S/N  | Playbook  | Description  | Usage  |
| ------------- | ------------- | ------------- | ------------- |
| 1 | add-yum-repo.yml  | To add a new Yum Repo for CentOS/Red Hat.<br>It has the option to disable all existing repos in `/etc/yum.repos.d`.  | 1. Update hosts and variables.<br>2. Execute the playbook:<br>`ansible-playbook add-yum-repo.yml`  |
| 2 | ansible-setup-clients.yml  | To setup individual Ansible client so that the Ansible master can communicate with this client.<br>It will create a non-root privilleged user for running Ansible tasks and also plant the ssh public key from the Ansible Master.  | 1. Update hosts and variables.<br>2. Execute the playbook:<br>`ansible-playbook ansible-setup-clients.yml --extra-vars "host=<ip-address>" -u <existing remote user> -k -K`<br>*where:<br>-u is your existing linux user<br>-k is user password<br>-K is your user sudo password*  |
| 3 | detect-family-distribution.yml  | To detect OS Family and Distribution.  | 1. Update hosts.<br>2. Execute the playbook:<br>`ansible-playbook detect-family-distribution.yml`  |
  
## Roles
| S/N  | Role  | Description  | Usage  |
| ------------- | ------------- | ------------- | ------------- |
| 1 | linux-updates  | To perform OS Updates for CentOS / RockyLinux / Red Hat / Ubuntu / Debian / Raspberry Pi OS.<br>It will reboot the host after updating and wait for the host to boot.<br>It has the options of enabling logging for both available updates and installed updates in the logging directory specified.  | 1. Update hosts in `linux-updates.yml`<br>2. Update variables in `roles/linux-updates/defaults/main.yml`<br>3. Execute the playbook:<br>`ansible-playbook linux-updates.yml`  |
| 2 | linux-fail2ban  | To setup Fail2ban for CentOS / RockyLinux / Ubuntu / Debian / Raspberry Pi OS.<br>Multiple failed ssh attempts will result in IP block in UFW/Firewalld.  | 1. Update hosts in `linux-fail2ban.yml`<br>2. Update variables in `roles/linux-fail2ban/defaults/main.yml`<br>3. Execute the playbook:<br>`ansible-playbook linux-fail2ban.yml`  |
| 3 | linux-docker  | To setup Docker for CentOS / RockyLinux / Ubuntu / Debian / Raspberry Pi OS.<br>It has the options of creating a user to manage Docker and installing Docker Compose.  | 1. Update hosts in `linux-docker.yml`<br>2. Update variables in `roles/linux-docker/defaults/main.yml`<br>3. Execute the playbook:<br>`ansible-playbook linux-docker.yml`  |
| 4 | linux-sssd  | To configure LDAP Client using SSSD for CentOS / RockyLinux / Ubuntu / Debian / Raspberry Pi OS so that the OS can be accessed by LDAP users.  | 1. Update hosts in `linux-sssd.yml`<br>2. Update variables in `roles/linux-sssd/defaults/main.yml`<br>3. Execute the playbook:<br>`ansible-playbook linux-sssd.yml`  |
  
