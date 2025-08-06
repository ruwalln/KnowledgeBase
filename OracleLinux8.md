# HowTo's using ORACLE LINUX 8

### HowTo use X11 applications on OEL8 on local machine using X11 GUI

user1 = root

```
xauth list $DISPLAY
oracle8linux1.localdomain/unix:  MIT-MAGIC-COOKIE-1  731f4bc2114420b228cb6a2ec58e2c54 <-- use this hex key for authorization

echo $DISPLAY
:0
```

user2 = oracle

```
DISPLAY=:0; export DISPLAY
xauth add $DISPLAY . 731f4bc2114420b228cb6a2ec58e2c54
```
Now you are able to start X11 applications using user2 authorization.

### HowTo to connect Putty to a virtual machine on VirtualBox 

Open Network Configuration on VirtualBox Machine Environment.
Next Click on "Port Forwarding/Port Weiterleitung"
check network configuration in terminal window on the guest machine.

#### check guest machine network configuration
```
[root@oracle8linux1 ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:0f:8e:55 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 brd 10.0.2.255 scope global dynamic noprefixroute enp0s3
       valid_lft 68904sec preferred_lft 68904sec
    inet6 fd17:625c:f037:2:a00:27ff:fe0f:8e55/64 scope global dynamic noprefixroute
       valid_lft 86155sec preferred_lft 14155sec
    inet6 fe80::a00:27ff:fe0f:8e55/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
3: virbr0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default qlen 1000
    link/ether 52:54:00:f5:7a:f2 brd ff:ff:ff:ff:ff:ff
    inet 192.168.122.1/24 brd 192.168.122.255 scope global virbr0
       valid_lft forever preferred_lft forever
```
#### configure VirtualBox Port Forwarding

In this case the guest machine is reachable using IP : 10.0.2.15/24
Click "add new port forwarding rule" in virtual machine configuration.

```
Name : TCPIP Forwarding PuTTy and X11
Protocol : TCP
Host IP : 127.0.0.1
Host Port : 1333
Guest IP : 10.0.2.15
Guest Port : 22
```

#### configure PuTTy to connect to VirtualBox guest machine

```
Hostname : 127.0.0.1 Port : 1333
Connection Type : SSH
X11 : [X] enable X11 forwarding
x display location : :0.0
MIT-Magic-Cookie-1
```
#### add Oracle User to sudo configuration 

- edit /etc/sudoers file and uncomment
- %wheel  ALL=(ALL)       ALL
- afterwards add user oracle to wheel group : usermod -aG wheel oracle

#### lock/unlock Users using passwd commands

- in case of locking and unlocking user acconts please use the passwd command (man passwd) for more informations.
- passwd -l <user> # lock user account
- passwd -u <user> # unlock user account
- passwd -e <user> # expire user account





