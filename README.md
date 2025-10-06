## Ansible role for setup XRAY server with 5 clients.
Was tested in Ubuntu server 24. \
***requirements:*** \
ansible - on the computer to run the installation \
python3 - on both computers \
\
Before starting playbook change inventory.ini: \
**ansible_user** - Create sudo user before runnnig playbook and generate ssh keys. [How to generate and add keys.](https://www.ssh.com/academy/ssh/keygen) \
**ansible_host** - The IP address of your VPS server for TCP/22 connection. \
and variables in /vless-server/vars/main.yml: \
**server_ip** - Your VPS server IP \
**vps_name** - Hostname for VPS \
**domain_name** - This is the domain of a real, popular website that your server will disguise itself as. \
\
For deployment server and generate clients config files run from Linux machine or Windows WSL: \
**ansible-playbook -i inventory.ini vless.yaml --ask-become-pass** \
\
Can also be used with configuration VLESS-WSS-Nginx.\
Edit /vless-server/tasks/main.yml
