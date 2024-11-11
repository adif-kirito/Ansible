# Network

Ping
```
ansible -m ping redhat
```

Routing Table
```
ansible -m command -a "netstat -rn" redhat
```

List ports
```
ansible -m command -a "netstat -tulpn" redhat
```

# Server

Disk space
```
ansible -m command -a "df -h" redhat
```

Memory
```
ansible -m command -a "free -h" redhat
```

CPU
```
ansible -m command -a "cat /proc/cpuinfo" redhat
```

Redhat version
```
ansible -m command -a "cat /etc/redhat-release" redhat
```

Server uptime
```
ansible -m command -a "uptime" redhat
```

Password policies
```
ansible -m command -a "cat /etc/pam.d/password-auth" redhat
```
