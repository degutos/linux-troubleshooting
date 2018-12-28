
# SSH troubleshooting

Scenario: User can't ssh

Troubleshooting Steps

- Check if different users are able to ssh
- Check if user with the issue can login to host as localhost and not ssh 
```
$ su - user
$ 
```
PS: if you able to login the issue might be with ssh service

- Check sshd service 

```
[root@andregonzaga1c ~]# systemctl status sshd
● sshd.service - OpenSSH server daemon
   Loaded: loaded (/usr/lib/systemd/system/sshd.service; enabled; vendor preset: enabled)
   Active: active (running) since Fri 2018-12-28 17:12:47 UTC; 1h 30min ago
     Docs: man:sshd(8)
           man:sshd_config(5)
  Process: 4936 ExecReload=/bin/kill -HUP $MAINPID (code=exited, status=0/SUCCESS)
 Main PID: 5633 (sshd)
   CGroup: /system.slice/sshd.service
           ├─5633 /usr/sbin/sshd -D
           ├─8098 sshd: root [priv]
           └─8099 sshd: root [net]

Dec 28 18:42:36 andregonzaga1c.mylabserver.com sshd[8098]: pam_succeed_if(sshd:auth): requirement "uid >= 1000" not met by user "root"
Dec 28 18:42:39 andregonzaga1c.mylabserver.com sshd[8098]: Failed password for root from 58.242.83.25 port 31446 ssh2
Dec 28 18:42:40 andregonzaga1c.mylabserver.com sshd[8098]: pam_succeed_if(sshd:auth): requirement "uid >= 1000" not met by user "root"
Dec 28 18:42:42 andregonzaga1c.mylabserver.com sshd[8098]: Failed password for root from 58.242.83.25 port 31446 ssh2
Dec 28 18:42:42 andregonzaga1c.mylabserver.com sshd[8098]: pam_succeed_if(sshd:auth): requirement "uid >= 1000" not met by user "root"
Dec 28 18:42:45 andregonzaga1c.mylabserver.com sshd[8098]: Failed password for root from 58.242.83.25 port 31446 ssh2
Dec 28 18:42:46 andregonzaga1c.mylabserver.com sshd[8098]: pam_succeed_if(sshd:auth): requirement "uid >= 1000" not met by user "root"
Dec 28 18:42:47 andregonzaga1c.mylabserver.com sshd[8098]: Failed password for root from 58.242.83.25 port 31446 ssh2
Dec 28 18:42:48 andregonzaga1c.mylabserver.com sshd[8098]: pam_succeed_if(sshd:auth): requirement "uid >= 1000" not met by user "root"
Dec 28 18:42:51 andregonzaga1c.mylabserver.com sshd[8098]: Failed password for root from 58.242.83.25 port 31446 ssh2
```

- Check Logs File

```
[root@andregonzaga1c ~]# tail /var/log/secure
```

```
[root@andregonzaga1c ~]# tail /var/log/messages
```

- Check password info

```
[root@andregonzaga1c ~]# chage -l linda
Last password change					: Dec 28, 2018
Password expires					: never
Password inactive					: never
Account expires						: never
Minimum number of days between password change		: 0
Maximum number of days between password change		: 99999
Number of days of warning before password expires	: 7
```

- Check passwd and shadow config file

```
[root@andregonzaga1c ~]# getent passwd linda
linda:x:1004:1005::/home/linda:/bin/bash
[root@andregonzaga1c ~]# getent shadow linda
linda:$6$0G5k4bVN$b5r8SVKDk3mtFWMilSJS0V9U5.9U0qBaEWHVk/UDjV3VpHIwkrBnD5xVHXt/pO87DSwozklHbc4tjDj6H.tFq.:17893:0:99999:7:::
```


