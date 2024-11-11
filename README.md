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

![alt text](https://github.com/adif-kirito/Ansible/blob/main/pic/anspic1.png)

### Add user to slave server

* Add user using the same credential as the step above to the slave server

### Configure ansible config file

1. Go to ansible directory - `cd /etc/ansible`
2. Edit `ansible.cfg` file. Must use **SUDO**
3. Uncomment the part shown below

![alt text](https://github.com/adif-kirito/Ansible/blob/main/pic/anspic2.png)

### Testing

* Run this command to test the connection to the slave server. The result must be green to confirm its success

![alt text](https://github.com/adif-kirito/Ansible/blob/main/pic/anspic3.png)

## Ansible Module Flag

|    Flag    |                                                      Purpose                                                     | Example                                                           | Explanation                                                                       |
|:----------:|:----------------------------------------------------------------------------------------------------------------:|-------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| -m shell   | Executes shell commands on the target hosts                                                                      | ansible -m shell -a "uptime" all                                  | Runs the uptime command on all hosts.                                             |
| -m command | Runs a command on the target nodes. This is similar to shell but more secure because it does not invoke a shell. | ansible -m command -a "ls /var/log" webservers                    | Lists files in the /var/log directory on all hosts in the webservers group        |
| -m copy    | Copies files from the control node to the target hosts                                                           | ansible -m copy -a "src=/etc/hosts dest=/tmp/hosts" redhat        | Copies the /etc/hosts file to /tmp/hosts on the target redhat host                |
| -m file    | Manages files and directories on the target nodes (e.g., create, delete, change permissions)                     | ansible -m file -a "path=/tmp/test state=directory mode=0755" all | Creates a directory /tmp/test with permissions 0755 on all hosts                  |
| -m service | Manages system services on the target hosts (e.g., start, stop, restart services)                                | ansible -m service -a "name=httpd state=started" web              | Ensures that the httpd service is running on all hosts in the web group           |
| -m user    | Manages user accounts on the target hosts                                                                        | ansible -m user -a "name=john state=present" all                  | Ensures that the user john exists on all target hosts                             |
| -m yum     | Manages packages with yum on Red Hat-based systems                                                               | ansible -m yum -a "name=nginx state=latest" redhat                | Installs or updates nginx to the latest version on the redhat hosts               |
| -m apt     | Manages packages with apt on Debian-based systems                                                                | ansible -m apt -a "name=nginx state=present" ubuntu               | Ensures nginx is installed on the ubuntu group of hosts                           |
| -m debug   | Prints variables or debug information to the console                                                             | ansible -m debug -a "msg='Hello World!'" all                      | Prints the message "Hello World!" on all target hosts                             |
| -m stat    | Checks the status of a file or directory on the target hosts.                                                    | ansible -m stat -a "path=/etc/passwd" all                         | Checks if the /etc/passwd file exists and gathers its details on all target hosts |
