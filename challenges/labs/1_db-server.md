# Data base Server

## * Hostname del nodo Server

```
[root@ip-10-1-2-237 centos]# hostname
ip-10-1-2-237.ec2.internal

```

## * Version

```
[root@ip-10-1-2-237 centos]# mysql --version
mysql  Ver 15.1 Distrib 5.5.56-MariaDB, for Linux (x86_64) using readline 5.1

```

## * Listar las bases de datos

```
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
+--------------------+
8 rows in set (0.00 sec)
```
