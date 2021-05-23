![GitHub](https://img.shields.io/github/license/d3athkai/MOTD-Login-Banner-for-Linux?style=plastic) ![GitHub](https://img.shields.io/badge/Python-2.7+-green?style=plastic) ![GitHub](https://img.shields.io/badge/Ansible-2.9+-blue?style=plastic)

# My Ansible Playbooks Roles

## Playbooks
| Playbook  | Description  | Usage  |
| ------------- | ------------- | ------------- |
| add-yum-repo.yml  | To add a Yum Repo for CentOS/Red Hat.  | 1. Update variables.<br>2. Execute the playbook:<br>`ansible-playbook add-yum-repo.yml`  |
| ansible-setup-clients.yml  | To setup individual Ansible client so that the Ansible master can communicate with this client.  | 1. Update variables.<br>2. Execute the playbook:<br>`ansible-playbook ansible-setup-clients.yml --extra-vars "host=<host name>" -u <existing remote user> -k -K`<br>*where:<br>-u is your existing linux user<br>-k is user password<br>-K is your user sudo password*  |

## Roles
| Role  | Description  | Usage  |
| ------------- | ------------- | ------------- |
| linux-updates  | To perform OS Updates for CentOS/Red Hat/Ubuntu/Debian/Raspberry Pi OS.  | 1. Update variables in `roles/linux-updates/defaults/main.yml`.<br>2. Execute the playbook:<br>`ansible-playbook linux-updates.yml`  |
  
