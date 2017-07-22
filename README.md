# ansible-dev
Ansible scripts that build a vagrant dev environment

# Instructions
1) In Vagrantfile
    1) Change IP
    2) Change synced folder
2) In ansible/playbook.retry
    1) Change IP
3) In ansible/vars/all.yml
    1) Change Nginx docroot
    2) Change IP
4) In ansible/inventories/dev
    1) Change IP
5) Create an ssh-key and put the contents of .pub into ansible/files/authorized_keys

# TODO
1) Make it more dynamic
    1) Set IP in one location
    2) Be able to use the same v.name
    3) Synced folder
