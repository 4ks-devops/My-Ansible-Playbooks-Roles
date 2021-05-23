![GitHub](https://img.shields.io/github/license/d3athkai/MOTD-Login-Banner-for-Linux?style=plastic) ![GitHub](https://img.shields.io/badge/Python-2.7+-green?style=plastic) ![GitHub](https://img.shields.io/badge/Ansible-2.9+-blue?style=plastic)

# My Ansible Playbooks and Roles
A work-in-progress with more Playbooks and Roles adding regularly.  

## Playbooks
| Playbook  | Description  | Usage  |
| ------------- | ------------- | ------------- |
| add-yum-repo.yml  | To add a new Yum Repo for CentOS/Red Hat.<br>It has the option to disable all existing repos in `/etc/yum.repos.d`.  | 1. Update hosts and variables.<br>2. Execute the playbook:<br>`ansible-playbook add-yum-repo.yml`  |
| ansible-setup-clients.yml  | To setup individual Ansible client so that the Ansible master can communicate with this client.<br>It will create a non-root privilleged user for running Ansible tasks and also plant the ssh public key from the Ansible Master.  | 1. Update hosts and variables.<br>2. Execute the playbook:<br>`ansible-playbook ansible-setup-clients.yml --extra-vars "host=<host name>" -u <existing remote user> -k -K`<br>*where:<br>-u is your existing linux user<br>-k is user password<br>-K is your user sudo password*  |
| detect-family-distribution.yml  | To detect OS Family and Distribution.  | 1. Update hosts.<br>2. Execute the playbook:<br>`ansible-playbook detect-family-distribution.yml`  |

## Roles
| Role  | Description  | Usage  |
| ------------- | ------------- | ------------- |
| linux-updates  | To perform OS Updates for CentOS / Red Hat / Ubuntu / Debian / Raspberry Pi OS.<br>It will reboot the host after updating and wait for the host to boot.<br>It has the options of enabling logging for both available updates and installed updates in the logging directory specified.  | 1. Update hosts in `linux-updates.yml`<br>2. Update variables in `roles/linux-updates/defaults/main.yml`<br>3. Execute the playbook:<br>`ansible-playbook linux-updates.yml`  |
  
