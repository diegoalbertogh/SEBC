# Iniciar CM Server

## * Primer linea del log:

```
[root@ip-10-1-2-185 centos]# head -n 1 /var/log/cloudera-scm-server/cloudera-scm-server.log
2017-12-01 11:16:30,105 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties, -Dfile.encoding=UTF-8, -Dcmf.root.logger=INFO,LOGFILE, -Dcmf.log.dir=/var/log/cloudera-scm-server, -Dcmf.log.file=cloudera-scm-server.log, -Dcmf.jetty.threshhold=WARN, -Dcmf.schema.dir=/usr/share/cmf/schema, -Djava.awt.headless=true, -Djava.net.preferIPv4Stack=true, -Dpython.home=/usr/share/cmf/python, -XX:+UseConcMarkSweepGC, -XX:+UseParNewGC, -XX:+HeapDumpOnOutOfMemoryError, -Xmx2G, -XX:MaxPermSize=256m, -XX:+HeapDumpOnOutOfMemoryError, -XX:HeapDumpPath=/tmp, -XX:OnOutOfMemoryError=kill -9 %p], Args: [], Version: 5.11.2 (#6 built by jenkins on 20170811-0014 git: 3c3ea33a12076fb83a8f11c4452c52fac685d01b)
```

## * Linea que contiene la frase "Started Jetty server":

```
[root@ip-10-1-2-185 centos]# cat /var/log/cloudera-scm-server/cloudera-scm-server.log | grep "Started Jetty server"
2017-12-01 11:17:38,884 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.

```

## * Contenido del archivo ```db.prorperties```

```
[root@ip-10-1-2-185 centos]# cat /etc/cloudera-scm-server/db.properties
# Auto-generated by scm_prepare_database.sh on Fri Dec  1 11:10:05 CST 2017
#
# For information describing how to configure the Cloudera Manager Server
# to connect to databases, see the "Cloudera Manager Installation Guide."
#
com.cloudera.cmf.db.type=mysql
com.cloudera.cmf.db.host=ip-10-1-2-237.ec2.internal
com.cloudera.cmf.db.name=scm
com.cloudera.cmf.db.user=scm
com.cloudera.cmf.db.setupType=EXTERNAL
com.cloudera.cmf.db.password=Scm_2017!
```