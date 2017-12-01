# sentry-test.md

## Relizar ejercicio donde:

* Configurar Sentry para hacer administrador a un usuario / grupo
* Verificar privilegios del usuario
* Crear un rol de Sentry con todas las autorizaciones
* Crear usuarios adicionales para el test
* Crear roles adicionales para el test 
* Otorgar diferentes privilegios a los usuarios
* Comprobar la diferencia de los resultados

## Output completo:

```
[centos@ip-10-1-2-209 ~]$ sudo su - test-user
Last login: Thu Nov 30 11:53:15 CST 2017 on pts/0
[test-user@ip-10-1-2-209 ~]$ beeline -u 'jdbc:hive2://ip-10-1-2-142.ec2.internal:10000/default;principal=hive/_HOST@CLOUDERA'
scan complete in 2ms
Connecting to jdbc:hive2://ip-10-1-2-142.ec2.internal:10000/default;principal=hive/_HOST@CLOUDERA
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
0: jdbc:hive2://ip-10-1-2-142.ec2.internal:10>
0: jdbc:hive2://ip-10-1-2-142.ec2.internal:10> show tables;
INFO  : Compiling command(queryId=hive_20171130120101_8dc577c3-f898-4656-9d23-3dcd75b2463f): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171130120101_8dc577c3-f898-4656-9d23-3dcd75b2463f); Time taken: 0.663 seconds
INFO  : Executing command(queryId=hive_20171130120101_8dc577c3-f898-4656-9d23-3dcd75b2463f): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171130120101_8dc577c3-f898-4656-9d23-3dcd75b2463f); Time taken: 0.381 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.379 seconds)
0: jdbc:hive2://ip-10-1-2-142.ec2.internal:10> show databases;
INFO  : Compiling command(queryId=hive_20171130120202_a2aedcf8-5169-48b4-ae1b-857020bf4277): show databases
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:database_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171130120202_a2aedcf8-5169-48b4-ae1b-857020bf4277); Time taken: 0.092 seconds
INFO  : Executing command(queryId=hive_20171130120202_a2aedcf8-5169-48b4-ae1b-857020bf4277): show databases
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171130120202_a2aedcf8-5169-48b4-ae1b-857020bf4277); Time taken: 0.146 seconds
INFO  : OK
+----------------+--+
| database_name  |
+----------------+--+
| default        |
+----------------+--+
1 row selected (0.306 seconds)
0: jdbc:hive2://ip-10-1-2-142.ec2.internal:10>


Script started on Thu 30 Nov 2017 12:58:35 PM CST
[centos@ip-10-1-2-209 ~]$ sudo su - george
Last login: Thu Nov 30 12:56:55 CST 2017 on pts/0
[george@ip-10-1-2-209 ~]$ kinit
Password for george@CLOUDERA: 
[george@ip-10-1-2-209 ~]$ 
[4P(reverse-i-search)`': beeline -u 'jdbc:hive2://ip-10-1-2-142.ec2.internal:10000/default;principal=hive/_HOST@CLOUDERA'
[george@ip-10-1-2-209 ~]$
scan complete in 2ms
Connecting to jdbc:hive2://ip-10-1-2-142.ec2.internal:10000/default;principal=hive/_HOST@CLOUDERA
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
0: jdbc:hive2://ip-10-1-2-142.ec2.internal:10> show tables;
INFO  : Compiling command(queryId=hive_20171130125959_1dd0ad2d-6567-4c47-8bb7-173c402d9549): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171130125959_1dd0ad2d-6567-4c47-8bb7-173c402d9549); Time taken: 0.079 seconds
INFO  : Executing command(queryId=hive_20171130125959_1dd0ad2d-6567-4c47-8bb7-173c402d9549): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171130125959_1dd0ad2d-6567-4c47-8bb7-173c402d9549); Time taken: 0.341 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.525 seconds)
0: jdbc:hive2://ip-10-1-2-142.ec2.internal:10> !exit
Closing: 0: jdbc:hive2://ip-10-1-2-142.ec2.internal:10000/default;principal=hive/_HOST@CLOUDERA
george@ip-10-1-2-209 ~]$ exit
logout
[centos@ip-10-1-2-209 ~]$ sudo su - ferdinand
[ferdinand@ip-10-1-2-209 ~]$ kinit 
Password for ferdinand@CLOUDERA: 
[ferdinand@ip-10-1-2-209 ~]$ beeline -u 'jdbc:hive2://ip-10-1-2-142.ec2.internal:10000/default;principal=hive/_HOST@CLOUDERA'
scan complete in 2ms
Connecting to jdbc:hive2://ip-10-1-2-142.ec2.internal:10000/default;principal=hive/_HOST@CLOUDERA
Connected to: Apache Hive (version 1.1.0-cdh5.12.1)
Driver: Hive JDBC (version 1.1.0-cdh5.12.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
Beeline version 1.1.0-cdh5.12.1 by Apache Hive
0: jdbc:hive2://ip-10-1-2-142.ec2.internal:10> show tables;
INFO  : Compiling command(queryId=hive_20171130125959_2688d322-a9e2-4741-af8e-7c39c6796f56): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171130125959_2688d322-a9e2-4741-af8e-7c39c6796f56); Time taken: 0.095 seconds
INFO  : Executing command(queryId=hive_20171130125959_2688d322-a9e2-4741-af8e-7c39c6796f56): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171130125959_2688d322-a9e2-4741-af8e-7c39c6796f56); Time taken: 0.263 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.453 seconds)
0: jdbc:hive2://ip-10-1-2-142.ec2.internal:10> !exit
Closing: 0: jdbc:hive2://ip-10-1-2-142.ec2.internal:10000/default;principal=hive/_HOST@CLOUDERA
[ferdinand@ip-10-1-2-209 ~]$ exit
logout
[centos@ip-10-1-2-209 ~]$ exit
exit

Script done on Thu 30 Nov 2017 12:59:42 PM CST

```
