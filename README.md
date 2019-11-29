# Vagrant to implement Ansible playbook to deploy MySQL Master-Slave replication in docker containers

### Requirement

- vagrant
- virtualbox
- ansible
- python
- python-pip

# MySQL Master-Slave
MySQL master-slave replication with Docker.

## Usage
```sh
git clone https://github.com/guidolarrain1981/vagrant-ansible-docker-mysql-master-slave.git
cd vagrant-ansible-docker-mysql-master-slave
vagrant up
```

#### Notes
This deploys a complete MySQL master-slave using docker images from https://github.com/guidolarrain1981/docker-mysql-master-slave forked from https://github.com/vbabak/docker-mysql-master-slave
