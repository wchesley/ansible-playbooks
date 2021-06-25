# Ansible Playbooks

This is a small collecion of Ansible playbooks I used to manage, maintian and deploy new VM's or LXC's on Proxmox. 

## Getting Started

### Requirements: 
- Proxmox 6.3+
- Ansible 2.7.7+ 
- python 3.7.3+

### Installing Ansible on Debian

Debian users may leverage the same source as the Ubuntu PPA.

Add the following line to `/etc/apt/sources.list`:

`deb http://ppa.launchpad.net/ansible/ansible/ubuntu trusty main`

Then run these commands:

```bash
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367
$ sudo apt update
$ sudo apt install ansible
```

Verify ansible installation with: 

`ansible all -m ping --ask-pass`

Guides to install on other distros are outlined in the ansible documentation: 

- [Installing Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- [Ansible Getting Started Guide](https://docs.ansible.com/ansible/latest/user_guide/intro_getting_started.html)

### Playbooks
- requires ansible host file with an `[Ubuntu]` header, and list of Ubuntu hosts, either by IP address or FQDN.
Run playbook to update all apt packages on Ubuntu hosts: 
`ansible-playbook update-ubuntu.yml -i /etc/ansible/hosts`