# 1_preinstall.md

Demostrar el contenido de:

* vm.swappiness

```
[centos@ip-10-1-2-209 vm]$ cat /proc/sys/vm/swappiness
1
[centos@ip-10-1-2-236 ~]$ cat /proc/sys/vm/swappiness
1
[centos@ip-10-1-2-142 ~]$ cat /proc/sys/vm/swappiness
1
[centos@ip-10-1-2-208 ~]$ cat /proc/sys/vm/swappiness
1

```

* Mount Volumenes

```
[centos@ip-10-1-2-209 vm]$ mount | grep xvd
/dev/xvda1 on / type xfs (rw,relatime,attr2,inode64,noquota)
/dev/xvdb1 on /disk1 type ext4 (rw,relatime,data=ordered)
/dev/xvdc1 on /disk2 type ext4 (rw,relatime,data=ordered)
[centos@ip-10-1-2-236 vm]$ mount | grep xvd
/dev/xvda1 on / type xfs (rw,relatime,attr2,inode64,noquota)
/dev/xvdb1 on /disk1 type ext4 (rw,relatime,data=ordered)
/dev/xvdc1 on /disk2 type ext4 (rw,relatime,data=ordered)
[centos@ip-10-1-2-142 vm]$ mount | grep xvd
/dev/xvda1 on / type xfs (rw,relatime,attr2,inode64,noquota)
/dev/xvdb1 on /disk1 type ext4 (rw,relatime,data=ordered)
/dev/xvdc1 on /disk2 type ext4 (rw,relatime,data=ordered)
[centos@ip-10-1-2-208 vm]$ mount | grep xvd
/dev/xvda1 on / type xfs (rw,relatime,attr2,inode64,noquota)
/dev/xvdb1 on /disk1 type ext4 (rw,relatime,data=ordered)
/dev/xvdc1 on /disk2 type ext4 (rw,relatime,data=ordered)
```

* Hugepage support

```
[centos@ip-10-1-2-209 vm]$ cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
[centos@ip-10-1-2-236 vm]$ cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
[centos@ip-10-1-2-142 vm]$ cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
[centos@ip-10-1-2-208 vm]$ cat /sys/kernel/mm/transparent_hugepage/defrag
always madvise [never]
```

* ifconfig

```
[centos@ip-10-1-2-209 vm]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 10.1.2.209  netmask 255.255.255.128  broadcast 10.1.2.255
        inet6 fe80::cf8:bdff:fef2:4246  prefixlen 64  scopeid 0x20<link>
        ether 0e:f8:bd:f2:42:46  txqueuelen 1000  (Ethernet)
        RX packets 4625991  bytes 5474347975 (5.0 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2294083  bytes 3613908145 (3.3 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 2140313  bytes 4596318699 (4.2 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2140313  bytes 4596318699 (4.2 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

[centos@ip-10-1-2-236 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 10.1.2.236  netmask 255.255.255.128  broadcast 10.1.2.255
        inet6 fe80::c1b:72ff:fe22:37f2  prefixlen 64  scopeid 0x20<link>
        ether 0e:1b:72:22:37:f2  txqueuelen 1000  (Ethernet)
        RX packets 2915136  bytes 3640326615 (3.3 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1735212  bytes 1154402963 (1.0 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 745582  bytes 526683862 (502.2 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 745582  bytes 526683862 (502.2 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

[centos@ip-10-1-2-208 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 10.1.2.208  netmask 255.255.255.128  broadcast 10.1.2.255
        inet6 fe80::c9c:99ff:fea2:b782  prefixlen 64  scopeid 0x20<link>
        ether 0e:9c:99:a2:b7:82  txqueuelen 1000  (Ethernet)
        RX packets 3037661  bytes 2992938266 (2.7 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2382243  bytes 2528743661 (2.3 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 784417  bytes 1199773831 (1.1 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 784417  bytes 1199773831 (1.1 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

[centos@ip-10-1-2-142 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 10.1.2.142  netmask 255.255.255.128  broadcast 10.1.2.255
        inet6 fe80::c00:d8ff:fec8:d1bc  prefixlen 64  scopeid 0x20<link>
        ether 0e:00:d8:c8:d1:bc  txqueuelen 1000  (Ethernet)
        RX packets 2163238  bytes 3387419421 (3.1 GiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2688453  bytes 2564948252 (2.3 GiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1  (Local Loopback)
        RX packets 249551  bytes 406168851 (387.3 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 249551  bytes 406168851 (387.3 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

* Resolver DNS 

```
[centos@ip-10-1-2-209 ~]$ ping www.google.com
PING www.google.com (172.217.7.228) 56(84) bytes of data.
64 bytes from iad23s58-in-f4.1e100.net (172.217.7.228): icmp_seq=1 ttl=48 time=1.27 ms
64 bytes from iad23s58-in-f4.1e100.net (172.217.7.228): icmp_seq=2 ttl=48 time=1.28 ms
64 bytes from iad23s58-in-f4.1e100.net (172.217.7.228): icmp_seq=3 ttl=48 time=1.28 ms
64 bytes from iad23s58-in-f4.1e100.net (172.217.7.228): icmp_seq=4 ttl=48 time=1.29 ms
64 bytes from iad23s58-in-f4.1e100.net (172.217.7.228): icmp_seq=5 ttl=48 time=1.31 ms
64 bytes from iad23s58-in-f4.1e100.net (172.217.7.228): icmp_seq=6 ttl=48 time=1.31 ms
64 bytes from iad23s58-in-f4.1e100.net (172.217.7.228): icmp_seq=7 ttl=48 time=1.28 ms
64 bytes from iad23s58-in-f4.1e100.net (172.217.7.228): icmp_seq=8 ttl=48 time=1.29 ms
64 bytes from iad23s58-in-f4.1e100.net (172.217.7.228): icmp_seq=9 ttl=48 time=1.47 ms
^C
--- www.google.com ping statistics ---
9 packets transmitted, 9 received, 0% packet loss, time 8009ms
rtt min/avg/max/mdev = 1.275/1.312/1.471/0.069 ms

```

* NSCD

```
[centos@ip-10-1-2-209 ~]$ service nscd status
Redirecting to /bin/systemctl status nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Wed 2017-11-29 19:26:35 CST; 1 day 2h ago
 Main PID: 645 (nscd)
   CGroup: /system.slice/nscd.service
           └─645 /usr/sbin/nscd

Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitored file `/etc/group` was written to
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/passwd` (61)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/group` (59)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/passwd` (61)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/group` (59)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 19:26:55 ip-10-1-2-209.ec2.internal nscd[645]: 645 checking for monitored file `/etc/netgroup': No such file or directory

[centos@ip-10-1-2-236 ~]$ service nscd status
Redirecting to /bin/systemctl status nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Wed 2017-11-29 19:26:35 CST; 1 day 2h ago
 Main PID: 645 (nscd)
   CGroup: /system.slice/nscd.service
           └─645 /usr/sbin/nscd

Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitored file `/etc/group` was written to
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/passwd` (61)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/group` (59)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/passwd` (61)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/group` (59)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 19:26:55 ip-10-1-2-209.ec2.internal nscd[645]: 645 checking for monitored file `/etc/netgroup': No such file or directory

[centos@ip-10-1-2-142 ~]$ service nscd status
Redirecting to /bin/systemctl status nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Wed 2017-11-29 19:26:35 CST; 1 day 2h ago
 Main PID: 645 (nscd)
   CGroup: /system.slice/nscd.service
           └─645 /usr/sbin/nscd

Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitored file `/etc/group` was written to
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/passwd` (61)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/group` (59)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/passwd` (61)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/group` (59)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 19:26:55 ip-10-1-2-209.ec2.internal nscd[645]: 645 checking for monitored file `/etc/netgroup': No such file or directory

[centos@ip-10-1-2-208 ~]$ service nscd status
Redirecting to /bin/systemctl status nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Wed 2017-11-29 19:26:35 CST; 1 day 2h ago
 Main PID: 645 (nscd)
   CGroup: /system.slice/nscd.service
           └─645 /usr/sbin/nscd

Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitored file `/etc/group` was written to
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/passwd` (61)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/group` (59)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/passwd` (61)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring file `/etc/group` (59)
Nov 30 12:50:38 ip-10-1-2-209.ec2.internal nscd[645]: 645 monitoring directory `/etc` (2)
Nov 30 19:26:55 ip-10-1-2-209.ec2.internal nscd[645]: 645 checking for monitored file `/etc/netgroup': No such file or directory

```

* NTPD

```
[centos@ip-10-1-2-209 ~]$ service ntpd status
Redirecting to /bin/systemctl status ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Wed 2017-11-29 19:26:35 CST; 1 day 2h ago
 Main PID: 643 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─643 /usr/sbin/ntpd -u ntp:ntp -g

[centos@ip-10-1-2-209 ~]$ service ntpd status
Redirecting to /bin/systemctl status ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Wed 2017-11-29 19:26:35 CST; 1 day 2h ago
 Main PID: 643 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─643 /usr/sbin/ntpd -u ntp:ntp -g

[centos@ip-10-1-2-209 ~]$ service ntpd status
Redirecting to /bin/systemctl status ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Wed 2017-11-29 19:26:35 CST; 1 day 2h ago
 Main PID: 643 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─643 /usr/sbin/ntpd -u ntp:ntp -g

[centos@ip-10-1-2-209 ~]$ service ntpd status
Redirecting to /bin/systemctl status ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Wed 2017-11-29 19:26:35 CST; 1 day 2h ago
 Main PID: 643 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─643 /usr/sbin/ntpd -u ntp:ntp -g
```
