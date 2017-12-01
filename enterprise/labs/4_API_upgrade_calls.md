# 4_API_upgrade_calls.md

## Usando la API por la linea de comandos, mostrar:

* Última version de la API disponible

```
[centos@ip-10-1-2-209 ~]$ curl -u diegoalbertogh:cloudera http://localhost:7180/api/version
v18
```

* Versión de Cloudera Manager 

```
[centos@ip-10-1-2-209 ~]$ curl -u diegoalbertogh:cloudera http://localhost:7180/api/v2/cm/version
{
  "version" : "5.13.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20171002-1719",
  "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
  "snapshot" : false
}
```

* Listar los usuarios de Cloudera Manager

```
[centos@ip-10-1-2-209 ~]$ curl -u diegoalbertogh:cloudera http://localhost:7180/api/v18/users
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "diegoalbertogh",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}
```

* Base de datos en uso por CM

```
[centos@ip-10-1-2-209 ~]$ curl -u diegoalbertogh:cloudera http://localhost:7180/api/v18/cm/scmDbInfo
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```
