# Dataproc Deployment

Automated deployment of a Python application behind Nginx using Ansible, Docker Compose, and systemd on Ubuntu Server 22.04

## Requirements

- Vagrant and VirtualBox
- Ansible installed on the host machine
- The community.general collection, if not already installed

## Setup and Deployment

1. Clone the repository if not yet done:

   git clone --branch release-v1 <REPOSITORY_URL>
   cd data_procesor

2. Start the virtual machine using the provided Vagrantfile:

   vagrant up

3. Configure inventory.ini using the SSH connection details provided by:

   vagrant ssh-config

   Update the host, port, username, and private key path as needed. Use the absolute path to avoid any issues. 

4. Test connectivity and deploy:

   ansible all -i inventory.ini -m ping
   ansible-playbook -i inventory.ini deploy.yml

## Verification

sudo systemctl status dataproc
sudo docker compose -f /opt/dataproc/docker-compose.yml ps
curl -i http://localhost:8080/

## Notes

Nginx access logs are available at /var/log/nginx/custom-access.log on the VM
