# 2_snapshot_test.md

## Relizar un directorio en el HDFS, cargar el archivo ZIP, posteriormente eliminarlo y volver a cargar mediante SNAPSHOT

```
[centos@ip-10-1-2-133 ~]$ ll
total 174396
-rw-r--r--. 1 root   root   174192082 Oct  9 17:05 jdk-8u152-linux-x64.rpm
drwxr-xr-x. 4 root   root         151 Sep 24  2016 mysql-connector-java-5.1.40
-rw-r--r--. 1 root   root     3911557 Sep 24  2016 mysql-connector-java-5.1.40.tar.gz
-rwxrwxr-x. 1 centos centos    474833 Nov 29 01:15 SEBC-master.zip
[centos@ip-10-1-2-133 ~]$ hadoop fs -mkdir /user/centos/precious
[centos@ip-10-1-2-133 ~]$ hadoop fs -put SEBC-master.zip /user/centos/precious/
[centos@ip-10-1-2-133 ~]$ hadoop fs -ls /user/centos/precious
Found 1 items
-rw-r--r--   3 centos centos     474833 2017-11-29 01:16 /user/centos/precious/SEBC-master.zip
[centos@ip-10-1-2-133 ~]$ hadoop fs -rm -r -skipTrash /user/centos/precious
rm: The directory /user/centos/precious cannot be deleted since /user/centos/precious is snapshottable and already has snapshots
[centos@ip-10-1-2-133 ~]$ hadoop fs -ls /user/centos/
Found 4 items
drwx------   - centos centos          0 2017-11-29 01:05 /user/centos/.staging
drwxr-xr-x   - centos centos          0 2017-11-29 01:18 /user/centos/precious
drwxr-xr-x   - centos centos          0 2017-11-29 00:23 /user/centos/source
drwxr-xr-x   - centos centos          0 2017-11-29 01:05 /user/centos/target
[centos@ip-10-1-2-133 ~]$ hadoop fs -rm -r -skipTrash /user/centos/precious/SEBC-master.zip
Deleted /user/centos/precious/SEBC-master.zip

```
