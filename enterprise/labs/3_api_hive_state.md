# 3_api_hive_state.md

## Detener, iniciar y mostrar el status del servicio HIVE mediante la linea de comandos utilizando la API

* Output 

```
Script started on Thu 30 Nov 2017 02:48:37 PM CST
[centos@ip-10-1-2-209 ~]$ curl -X POST -u diegoalbertogh:cloudera http://localhost:7180/api/v2/clusters/diegoalbertogh/services/hive/commands/stop
{
  "id" : 563,
  "name" : "Stop",
  "startTime" : "2017-11-30T20:48:47.395Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}[centos@ip-10-1-2-209 ~]$ curl -X POST -u diegoalbertogh:cloudera http://localhost:7180/api/v2/clusters/diegoalbertogh/services/hive/commands/start
{
  "id" : 568,
  "name" : "Start",
  "startTime" : "2017-11-30T20:49:15.927Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}[centos@ip-10-1-2-209 ~]$ curl -u diegoalbertogh:cloudera http://localhost:7180/api/v2/clusters/diegoalbertogh/services/hive
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-10-1-2-209.ec2.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
}[centos@ip-10-1-2-209 ~]$ exit
exit

Script done on Thu 30 Nov 2017 02:50:17 PM CST

```
