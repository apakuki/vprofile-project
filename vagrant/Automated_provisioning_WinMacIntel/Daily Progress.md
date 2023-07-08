### 04/07/2023

## VProfile App continuation - Automated Provisioning

* Running the automated provisioning script
- web01 wasn't getting an ip address
- web01 was failing ssh

After searching manually added ip bridged to the WIFI interface as follows:
Got help '#ip addr help'


root@ubuntu-jammy:/etc/netplan# ip addr add 192.168.56.11/24 dev enp0s8
root@ubuntu-jammy:/etc/netplan# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 02:47:6c:86:7f:19 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 metric 100 brd 10.0.2.255 scope global dynamic enp0s3
       valid_lft 85774sec preferred_lft 85774sec
    inet6 fe80::47:6cff:fe86:7f19/64 scope link 
       valid_lft forever preferred_lft forever
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:46:13:81 brd ff:ff:ff:ff:ff:ff
    inet 192.168.56.11/24 scope global enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe46:1381/64 scope link 
       valid_lft forever preferred_lft forever
root@ubuntu-jammy:/etc/netplan# 

