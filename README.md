# Vagrant Ubuntu 22.04 Virtual Machine Provisioned By Ansible

This repository provides a Vagrant configuration to create an Ubuntu 22.04 virtual machine using VirtualBox, along with ansible roles environment. 

## Prerequisites

Before you begin, ensure you have the following software installed on your local machine:

- [Vagrant](https://www.vagrantup.com/downloads)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
- [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Getting Started
### 1. Create Directory called Vagrant (optional name)
```
mkdir Vagrant
```
### 2. Clone this repository to your local machine:
```
git clone https://github.com/mahmoud-sabra/Vagrant.git
```
### 3. Generate SSH Key Pair: If you want SSH key authentication, generate a key pair on your local machine:
```
ssh-keygen 
```
### 4.Enter file in which to save the key:
```
/home/username/Vagrant/users/files
```

### 5. Start the virtual machine by running:

```
vagrant up
```
----
## Provisioning
**We Have 3 roles**

1. users
2. Lempstack
3. Lampstack

### Provision with users
> add users to vagrant machine & make sure their home directory created and .ssh directory and inside it authorized_keys file are there
> and their permissions 0700 > .ssh && 0600 > .ssh/authorized_keys

```
ansible-playbook -i inventory users.yml
```
### Provision with Lempstack
> Updates and upgrades the system && Install MySQL, PHP, nginx

```
ansible-playbook -i inventory lempstack.yml
```
### Provision with Lampstack
> Updates and upgrades the system && Install MySQL, PHP, apache

```
ansible-playbook -i inventory lampstack.yml
```
## Clean Up

Halt and remove the VM:

```
vagrant halt
```
```
vagrant destroy
```
