# Boot Issue

## Rescue Disk

- We need a CD-Rom or USB bootable with OS version
- We need interrupt the boot before load the Grub. Usually `escape` key or some special keys will guide us to the boot options
- Boot by Cd-Rom
- Select Troubleshooting
- Select Rescue CentOS System
- The system will mont /mnt/sysimage. Accept that by choosing option 1 Continue

#### To check filesystems and chroot
`$ mount` 


```
$ chroot /mnt/sysimage
```

- We can troubleshooting from here

## Rd.break - interrupting normal boot

- on Grub menu, type `e` to edit options
- on `linux16` line add the option `rd.break` and remove rhgb quiet (to see msgs during boot)

#### Check filesystem

```
$ mount
``` 

Check for the line 
`/dev/mapper/centos-root   on /sysroot`
as `r` (read)

#### Mounting filesystem

```
$ mount -o remount,rw /sysroot
$ chroot /sysroot
```

#### optional proc mount 

```
$ mount -t proc proc /proc
```

- At this point we can troubleshoot

## init=/bin/bash



