# Gathering info

### Check logs since last reboot

```
[root@andregonzaga1c ~]# journalctl 
```

### Check logs -ef - (end, follow)

```
[root@andregonzaga1c ~]# journalctl -ef
```

###  show logs for specific service

```
[root@andregonzaga1c ~]# journalctl _SYSTEMD_UNIT=sshd.service
```

### show logs for specific service

```
[root@andregonzaga1c ~]# journalctl -u sshd.service
```

### show logs for emerg error

```
[root@andregonzaga1c ~]# journalctl -p emerg..err
```

### Show logs from regarding to last boot

```
[root@andregonzaga1c ~]# journalctl -xb
```

### show logs during specific time

```
[root@andregonzaga1c ~]# journalctl --since "2019-01-02 14:00:00" --until "2019-01-02 14:10:00"
```

### show logs with lots of details 

```
[root@andregonzaga1c ~]# journalctl -o verbose
```

# Making persistent log with journalctl

```
[root@andregonzaga1c ~]# vi /etc/systemd/journald.conf 
```

- check if Storage=auto

```
[Journal]
#Storage=auto
```

### Create /var/log/journal

`[root@andregonzaga1c ~]# mkdir /var/log/journal/`

### Change permission and owner

```
[root@andregonzaga1c ~]# chown root.systemd-journal journal/
[root@andregonzaga1c ~]# chmod 2755 /var/log/journal/
```

### restart process

```
[root@andregonzaga1c ~]# killall -USR1 systemd-journald
```

- After that reboot server and check again `journalctl`






