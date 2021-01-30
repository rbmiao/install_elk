
# Install and configure ELK on RHEL/CentOS 7

- Ansible server: Macbook pro
- Ansible client: vagrant vm, craeted by Vagrantfile
- On macbook, add following to /etc/hosts:
```
192.168.2.102	devops1
```

 At the moment, ansible running with username:vagrant, password: vagrant

 In order to run playbook, promote vagrant user to root in main.yml
```
  become: yes
  become_user: root
```

 In order to run ansible playbook, git clone the directory, navigate to the directory
```
cd install_elk
vagrant up
```
 After VM is up, check whether ansible can communicate with vm,
```
ansible all -i inv -m ping
```
If above step returns green, run following command to deploy elk on newly created vm
```
ansible-playbook -i inv main.yaml
```

### Login to kibana http://devops1, username: kibana, password: kibana



============


### This playbook will do the following:
* Install and configure ELK stack based on the inventory
* Install front end web server
* Configure customized directories to manage index data
* Secure Kibana, can be accessed only through the front end web server
* Front end web server secured using htpasswd
* Install and configure Curator for log cleanups

### Default kibana credentials: user:kibana password:kibana
