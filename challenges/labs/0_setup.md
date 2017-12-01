# 0_setup.md

## Proveedor Cloud 
	* AWS

## IP de las Instancias 
10.1.2.237
10.1.2.185
10.1.2.195
10.1.2.241

## S.O. Linux 
	* Centos 7

## Capacidad del File Sistem
	* 50 GB

## Comando ```yum repolist enabled``` 
	* Output
```
[root@ip-10-1-2-237 centos]# yum repolist enabled
Loaded plugins: fastestmirror
base                                                                                                                                                                     | 3.6 kB  00:00:00
extras                                                                                                                                                                   | 3.4 kB  00:00:00
updates                                                                                                                                                                  | 3.4 kB  00:00:00
(1/4): base/7/x86_64/group_gz                                                                                                                                            | 156 kB  00:00:00
(2/4): extras/7/x86_64/primary_db                                                                                                                                        | 130 kB  00:00:00
(3/4): base/7/x86_64/primary_db                                                                                                                                          | 5.7 MB  00:00:02
(4/4): updates/7/x86_64/primary_db                                                                                                                                       | 3.6 MB  00:00:04
Determining fastest mirrors
 * base: mirror.cs.pitt.edu
 * extras: mirror.vtti.vt.edu
 * updates: mirror.es.its.nyu.edu
repo id                                                                                     repo name                                                                                     status
base/7/x86_64                                                                               CentOS-7 - Base                                                                               9,591
extras/7/x86_64                                                                             CentOS-7 - Extras                                                                               283
updates/7/x86_64                                                                            CentOS-7 - Updates                                                                            1,134
repolist: 11,008

```
*****************************************************************************************************

## Listar usuarios creados dentro del archivo ```/etc/passwd```

* output

```
[root@ip-10-1-2-237 centos]# cat /etc/passwd | egrep "saturn|haley"
saturn:x:2800:1002::/home/saturn:/bin/bash
haley:x:2900:1001::/home/haley:/bin/bash
```
