# Monitoring tools
### Installing Cockpit to monitoring

```
[root@andregonzaga1c ~]# yum search cockpit
```

```
[root@andregonzaga1c ~]# yum install cockpit cockpit-system cockpit-storaged cockpit-pcp
```

#### Enabling Service cockpit

```
[root@andregonzaga1c ~]# systemctl enable --now cockpit.socket 
```

#### Enabling Firewall for cockpit

```
[root@andregonzaga1c ~]# firewall-cmd --permanent --add-service=cockpit
success
[root@andregonzaga1c ~]# firewall-cmd --reload
success
```


