# HDFS 

## Output del comando ```hdfs dfs -ls /user```

```
[hdfs@ip-10-1-2-237 ~]$ hdfs dfs -ls /user
Found 7 items
drwxr-xr-x   - haley  haley           0 2017-12-01 12:08 /user/haley
drwxrwxrwx   - mapred hadoop          0 2017-12-01 12:02 /user/history
drwxrwxr-t   - hive   hive            0 2017-12-01 12:03 /user/hive
drwxrwxr-x   - hue    hue             0 2017-12-01 12:06 /user/hue
drwxrwxr-x   - oozie  oozie           0 2017-12-01 12:04 /user/oozie
drwxr-xr-x   - saturn saturn          0 2017-12-01 12:08 /user/saturn
drwxr-x--x   - spark  spark           0 2017-12-01 12:02 /user/spark
```

## Output del comando ```../api/v14/hosts```

```
[centos@ip-10-1-2-185 ~]$ curl -u admin:admin http://ec2-35-153-68-82.compute-1.amazonaws.com:7180/api/v14/hosts
{
  "items" : [ {
    "hostId" : "9333c52e-38b4-46ff-9a58-e23a75e9a5f5",
    "ipAddress" : "10.1.2.185",
    "hostname" : "ip-10-1-2-185.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/hostRedirect/9333c52e-38b4-46ff-9a58-e23a75e9a5f5",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31453491200
  }, {
    "hostId" : "4b71a099-c927-4c1b-8f9d-09b018475687",
    "ipAddress" : "10.1.2.195",
    "hostname" : "ip-10-1-2-195.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/hostRedirect/4b71a099-c927-4c1b-8f9d-09b018475687",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31453491200
  }, {
    "hostId" : "c87574d9-20b4-4951-8b66-37013269e649",
    "ipAddress" : "10.1.2.237",
    "hostname" : "ip-10-1-2-237.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/hostRedirect/c87574d9-20b4-4951-8b66-37013269e649",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31453491200
  }, {
    "hostId" : "2b7273e7-4fb9-4cae-90a7-cca12c520881",
    "ipAddress" : "10.1.2.241",
    "hostname" : "ip-10-1-2-241.ec2.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/hostRedirect/2b7273e7-4fb9-4cae-90a7-cca12c520881",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 8,
    "numPhysicalCores" : 4,
    "totalPhysMemBytes" : 31453491200
  } ]
}
```

## Output del comando ```../api/v8/clusters/diegoalbertogh/services```

```
[centos@ip-10-1-2-185 ~]$ curl -u admin:admin http://ec2-35-153-68-82.compute-1.amazonaws.com:7180/api/v8/clusters/diegoalbertogh/services/
{
  "items" : [ {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/serviceRedirect/hive",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HIVE_HIVEMETASTORES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HIVE_HIVESERVER2S_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hive"
  }, {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/serviceRedirect/zookeeper",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "ZOOKEEPER_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "ZOOKEEPER_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "ZooKeeper"
  }, {
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/serviceRedirect/hue",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/serviceRedirect/oozie",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Oozie"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/serviceRedirect/yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)"
  }, {
    "name" : "spark_on_yarn",
    "type" : "SPARK_ON_YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/serviceRedirect/spark_on_yarn",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Spark"
  }, {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://ip-10-1-2-185.ec2.internal:7180/cmf/serviceRedirect/hdfs",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD"
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD"
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS"
  } ]
}
```
