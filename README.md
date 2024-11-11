# Ansible

## What is Ansible

Ansible is an open-source automation tool used for IT tasks like configuration management, application deployment, and orchestration. It simplifies the management of complex systems by automating routine tasks without needing custom scripts or complex programming.

## Installation Step

Install Ansible

```
sudo apt install ansible
```

Install sshpass

```
sudo apt install sshpass
```

## Setting Up

### Add Host to Group

1. Go to ansible directory - `cd /etc/ansible`
2. Edit `hosts` file. Must use **SUDO**
3. At the bottom, add server hostname and ip address. Add also the username and password to connect to the slave server.

![alt text]([http://url/to/img.png](https://github.com/adif-kirito/Ansible/blob/main/pic/anspic1.png))
