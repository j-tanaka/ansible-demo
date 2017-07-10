# ansible-demo

About
-----
This repository is aimed to developing ansible-playbooks that setup useful tools or systems.

Usage
-----

### setup-goofys.yml
This playbook provides you goofys installation with ease.

if you'd like to install goofys on your own machine, please do following three steps.

1. Set AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY on secrets/secret_vars.yml

[secrets/secret_vars.yml]

```yml
---
aws_access_key_id: xxxxx
aws_secret_access_key: xxxxx
```

2. Change AWS_DEFAULT_REGION on goofys-install.yml file if you want. (ap-northeast-1 TOKYO is default.)

3. execute ansible playbook with sudo password. if you like to execute this playbook on remote machine, you have to delete "connection" paramete and change "hosts" parameter to hosts group depending on inventory file. 

```
$ ansible-playbook setup-goofys.yml -i
```

(if you execute playbook with inventory/inventory.ini file.)
```
$ ansible-playbook -i inventory/inventory.ini setup-goofys.yml -K
```
