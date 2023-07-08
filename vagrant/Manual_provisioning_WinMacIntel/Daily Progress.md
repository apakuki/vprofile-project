### 03/07/2023

# VM Setup

* Setup of Vagrant to bootstrap 5 VMs for each component of the stack

* Setup of MySQL Database, MCache and RabbitMQ servers 


apakuki@macbookpro-ubuntu:~/Documents/vprofile-project/vagrant/Manual_provisioning_WinMacIntel$ vagrant up
Bringing machine 'db01' up with 'virtualbox' provider...
Bringing machine 'mc01' up with 'virtualbox' provider...
Bringing machine 'rmq01' up with 'virtualbox' provider...
Bringing machine 'app01' up with 'virtualbox' provider...
Bringing machine 'web01' up with 'virtualbox' provider...
==> db01: Checking if box 'eurolinux-vagrant/centos-stream-9' version '9.0.25' is up to date...
==> db01: [vagrant-hostmanager:guests] Updating hosts file on active guest virtual machines...
    db01: 
    db01: Inserting generated public key within guest...
    db01: Removing insecure key from the guest if it's present...
    db01: Key inserted! Disconnecting and reconnecting using new SSH key...
    mc01: 
    mc01: Inserting generated public key within guest...
    mc01: Removing insecure key from the guest if it's present...
    mc01: Key inserted! Disconnecting and reconnecting using new SSH key...
    app01: 
    app01: Inserting generated public key within guest...
    app01: Removing insecure key from the guest if it's present...
    app01: Key inserted! Disconnecting and reconnecting using new SSH key...
    rmq01: 
    rmq01: Inserting generated public key within guest...
    rmq01: Removing insecure key from the guest if it's present...
    rmq01: Key inserted! Disconnecting and reconnecting using new SSH key...
==> db01: [vagrant-hostmanager:host] Updating hosts file on your workstation (password may be required)...
==> db01: Machine already provisioned. Run `vagrant provision` or use the `--provision`
==> db01: flag to force provisioning. Provisioners marked to run always will still run.
==> mc01: Checking if box 'eurolinux-vagrant/centos-stream-9' version '9.0.25' is up to date...
==> mc01: [vagrant-hostmanager:guests] Updating hosts file on active guest virtual machines...
==> mc01: [vagrant-hostmanager:host] Updating hosts file on your workstation (password may be required)...
==> mc01: Machine already provisioned. Run `vagrant provision` or use the `--provision`
==> mc01: flag to force provisioning. Provisioners marked to run always will still run.
==> rmq01: Checking if box 'eurolinux-vagrant/centos-stream-9' version '9.0.25' is up to date...
==> rmq01: [vagrant-hostmanager:guests] Updating hosts file on active guest virtual machines...
==> rmq01: [vagrant-hostmanager:host] Updating hosts file on your workstation (password may be required)...
==> rmq01: Machine already provisioned. Run `vagrant provision` or use the `--provision`
==> rmq01: flag to force provisioning. Provisioners marked to run always will still run.
==> app01: Checking if box 'eurolinux-vagrant/centos-stream-9' version '9.0.25' is up to date...
==> app01: [vagrant-hostmanager:guests] Updating hosts file on active guest virtual machines...
==> app01: [vagrant-hostmanager:host] Updating hosts file on your workstation (password may be required)...
==> app01: Machine already provisioned. Run `vagrant provision` or use the `--provision`
==> app01: flag to force provisioning. Provisioners marked to run always will still run.
==> web01: Checking if box 'ubuntu/jammy64' version '20230616.0.0' is up to date...
==> web01: Resuming suspended VM...
==> web01: Booting VM...
==> web01: Waiting for machine to boot. This may take a few minutes...
    web01: SSH address: 127.0.0.1:2203
    web01: SSH username: vagrant
    web01: SSH auth method: password
    web01: Warning: Authentication failure. Retrying...
    web01: Warning: Authentication failure. Retrying...
    web01: Warning: Authentication failure. Retrying...
    web01: Warning: Authentication failure. Retrying...
    web01: Warning: Authentication failure. Retrying...
    web01: Warning: Authentication failure. Retrying...
    web01: Warning: Authentication failure. Retrying...
    web01: Warning: Authentication failure. Retrying...
    web01: Warning: Authentication failure. Retrying...
    web01: Warning: Authentication failure. Retrying...
    web01: Warning: Authentication failure. Retrying...
^C==> web01: Waiting for cleanup before exiting...
    web01: Warning: Connection refused. Retrying...
Vagrant exited after cleanup due to external interrupt.
apakuki@macbookpro-ubuntu:~/Documents/vprofile-project/vagrant/Manual_provisioning_WinMacIntel$ vagrant up web01
Bringing machine 'web01' up with 'virtualbox' provider...
==> web01: Checking if box 'ubuntu/jammy64' version '20230616.0.0' is up to date...
==> web01: [vagrant-hostmanager:guests] Updating hosts file on active guest virtual machines...
==> web01: [vagrant-hostmanager:host] Updating hosts file on your workstation (password may be required)...
apakuki@macbookpro-ubuntu:~/Documents/vprofile-project/vagrant/Manual_provisioning_WinMacIntel$ vagrant global-status
id       name   provider   state   directory                                                                        
--------------------------------------------------------------------------------------------------------------------
ab6ef54  db01   virtualbox running /home/apakuki/Documents/vprofile-project/vagrant/Manual_provisioning_WinMacIntel 
abe7130  mc01   virtualbox running /home/apakuki/Documents/vprofile-project/vagrant/Manual_provisioning_WinMacIntel 
b144337  rmq01  virtualbox running /home/apakuki/Documents/vprofile-project/vagrant/Manual_provisioning_WinMacIntel 
0edbef3  app01  virtualbox running /home/apakuki/Documents/vprofile-project/vagrant/Manual_provisioning_WinMacIntel 
e8d6454  web01  virtualbox running /home/apakuki/Documents/vprofile-project/vagrant/Manual_provisioning_WinMacIntel 
 
The above shows information about all known Vagrant environments
on this machine. This data is cached and may not be completely
up-to-date (use "vagrant global-status --prune" to prune invalid
entries). To interact with any of the machines, you can go to that
directory and run Vagrant, or you can use the ID directly with
Vagrant commands from any directory. For example:
"vagrant destroy 1a2b3c4d"
apakuki@macbookpro-ubuntu:~/Documents/vprofile-project/vagrant/Manual_provisioning_WinMacIntel$ 

### 04/07/2023

* Installed Tomcat - Apache/Java server
* Installed Web server

## VProfile App continuation - Automated Provisioning

* Running the automated provisioning script
- web01 wasn't getting an ip address
- web01 was failing ssh

After searching manually added ip bridged to the WIFI interface as follows:
Got help '#ip addr help'


* Asked questions in the Q&A section of the course:


VProfile - VMs not getting vagrant configured IP addresses.
0 upvotes
Apakuki · Lecture 21 · 4 days ago
Hi Imran and colleagues!

First off, huge thanks to the Imran for putting this course together! I am absolutely engrossed in the content!



Platform:
I am running Ubuntu on an old Macbook Pro (2012) with an i5 processor, 16GB RAM, 1TB SSD



Issue:

Since starting the course some weird things have been happening with vagrant and virtualbox. In particular, the ip addresses configured in the Vagrantfile config are not picked up by the VMs. I have manually removed configured IP and replaced with the ip addressing scheme in the course notes.



[root@db01 ~]# ip addr del 192.168.56.123/24 dev enp0s8

[root@db01 ~]# ip addr add 192.168.56.15/24 broadcast 192.168.56.255 dev enp0s8  noprefixroute



Secondly, ssh seems to fail on some distributions (CentOS & Ubuntu) so I have been going back and forward between Virtualbox terminal and Vagrant config to eventually get into the VMs



Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true 
  config.hostmanager.manage_host = true
  config.ssh.username = "vagrant"
  config.ssh.password = "vagrant"


Then editing the /etc/ssh/sshd_config file to allow ssh with pasword



So now that I have all the VMs working with all the required daemons restarted and enabled, all firewalls are off, I still can't seem to get the http://web01 to come up in my browser?

Some pointers on where the problem lays would be very much appreciated.

* Found Answer:


Apakuki
0 upvotes
3 days ago
FIXED:



It's really weird!



So Vagrant didn't add ip addresses and/or network to the routing table for the some VMs, I had to check each of the VMs and added correct IP and/or network to the routing table. Even more weird is that there was a configured IP for the target network (in my case 192.168.56.124 instead of 192.168.56.14) after I added the correct IP and removed the 'other' IP, but after a while it (the 'other' IP) would reappear. So I just left both of them there to get the web01 site to come up.



Commands used:

*Add IP

root@web01:~# ip addr add 192.168.56.11/24 broadcast 192.168.56.255 dev enp0s8  noprefixroute


*Add Route

root@web01:/etc/netplan# route add -net 192.168.56.0/24  dev enp0s8



*Verify

root@web01:/etc/netplan# ip addr show

root@web01:/etc/netplan# route

---
root@web01:~# ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 02:47:6c:86:7f:19 brd ff:ff:ff:ff:ff:ff
    inet 10.0.2.15/24 metric 100 brd 10.0.2.255 scope global dynamic enp0s3
       valid_lft 54118sec preferred_lft 54118sec
    inet6 fe80::47:6cff:fe86:7f19/64 scope link 
       valid_lft forever preferred_lft forever
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:46:13:81 brd ff:ff:ff:ff:ff:ff
    inet 192.168.56.11/24 brd 192.168.56.255 scope global noprefixroute enp0s8
       valid_lft forever preferred_lft forever
    inet6 fe80::a00:27ff:fe46:1381/64 scope link 
       valid_lft forever preferred_lft forever
root@web01:~# route
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
default         _gateway        0.0.0.0         UG    100    0        0 enp0s3
10.0.2.0        0.0.0.0         255.255.255.0   U     100    0        0 enp0s3
_gateway        0.0.0.0         255.255.255.255 UH    100    0        0 enp0s3
10.0.2.3        0.0.0.0         255.255.255.255 UH    100    0        0 enp0s3
192.168.56.0    0.0.0.0         255.255.255.0   U     0      0        0 enp0s8
root@web01:~# 
root@web01:~# ping db01
PING db01 (192.168.56.15) 56(84) bytes of data.
64 bytes from db01 (192.168.56.15): icmp_seq=1 ttl=64 time=1.64 ms
64 bytes from db01 (192.168.56.15): icmp_seq=2 ttl=64 time=1.29 ms
64 bytes from db01 (192.168.56.15): icmp_seq=3 ttl=64 time=1.42 ms
^C
--- db01 ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2005ms
rtt min/avg/max/mdev = 1.286/1.450/1.642/0.146 ms
root@web01:~# 





