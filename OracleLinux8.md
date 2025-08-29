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
- passwd -l **username** # lock user account
- passwd -u **username** # unlock user account
- passwd -e **username** # expire user account

#### truncate logfiles and other text based files

- truncate --size=0K **filename** # truncate filename to 0K
- or use > **filename** # truncate filename

#### Working with Private/Public KeyPairs

1. generate a private/public rsa keypair using Oracle Linux 8
```
ssh-keygen -t rsa -N '' -b 2048 -C 'Public and Private KeyPair' -f /root/Dokumente/keys/.ssh/id_rsa
```
2. use ssh-copy-id to add the generated public key to "authorized_keys" '/root/.ssh/authorized_keys
```
ssh-copy-id -i id_rsa.pub root@oracle8linux1
```
3. copy the private-key as a file inside a folder and convert the file to Putty .ppk format using PuttyGen
use "Load Private Key" and press "Save Private Key" using *.PPK format
4. Load the session inside Putty and configure in SSH/Auth/Credentials click on "Private Key File" Browse using the converted private keyfile.
5. Click on "Session" and press "Save" to save configuration to template.
6. Logon to the Server and enter your username .. and now you are logged in without using a password.

#### PSCP - Copy files from Windows to Linux using Public Key Pairs without password

1. You need the .PPK KeyName and FilePath - be sure you have one
2. Open a Command Window on Windows Machine inside the PuTTY tools folder and use the following options:
   
- pscp.exe
- -v = verbose
- -i "C:\Users\zbook\Downloads\putty\oracle_id_rsa.ppk" = Path to the public key
- -P 1333 = Port to connect to
- C:\Users\zbook\OneDrive\Documents\work\psconvert.csv = source filename to transfer
- user@hostname:destination_filename = oracle@oracle8linux1:psconvert.csv

```
C:\Users\zbook\Downloads\putty>pscp -v -i "C:\Users\zbook\Downloads\putty\oracle_id_rsa.ppk" -P 1333 C:\Users\zbook\OneDrive\Documents\work\psconvert.csv oracle@oracle8linux1:psconvert.csv
Looking up host "127.0.0.1" for SSH connection
Connecting to 127.0.0.1 port 1333
Connected to 127.0.0.1 (from 127.0.0.1:54369)
We claim version: SSH-2.0-PuTTY_Release_0.83
Remote version: SSH-2.0-OpenSSH_8.0
Using SSH protocol version 2
No GSSAPI security context available
Enabling strict key exchange semantics
Doing ECDH key exchange with curve Curve25519, using hash SHA-256 (unaccelerated)
Server also has ecdsa-sha2-nistp256/rsa-sha2-512/rsa-sha2-256/ssh-rsa host keys, but we don't know any of them
Host key fingerprint is:
ssh-ed25519 255 SHA256:UeeuCllp+2rxAuj3JH/AaNmirUM3yoAoVg5kbeaima0
Initialised AES-256 SDCTR (AES-NI accelerated) outbound encryption
Initialised HMAC-SHA-256 (unaccelerated) outbound MAC algorithm
Initialised AES-256 SDCTR (AES-NI accelerated) inbound encryption
Initialised HMAC-SHA-256 (unaccelerated) inbound MAC algorithm
Reading key file "C:\Users\zbook\Downloads\putty\oracle_id_rsa.ppk"
Using username "oracle".
Offered public key
Offer of public key accepted
Authenticating with public key "Public and Private KeyPair"
Sent public key signature
Access granted
Opening main session channel
Remote debug message: /home/oracle/.ssh/authorized_keys:1: key options: agent-forwarding port-forwarding pty user-rc x11-forwarding
Remote debug message: /home/oracle/.ssh/authorized_keys:1: key options: agent-forwarding port-forwarding pty user-rc x11-forwarding
Opened main channel
Started a shell/command
Using SFTP
Connected to 127.0.0.1
Sending file psconvert.csv, size=6922134
psconvert.csv             | 6759 kB | 6759.9 kB/s | ETA: 00:00:00 | 100%
Session sent command exit status 0
Main session channel closed
All channels closed
```



