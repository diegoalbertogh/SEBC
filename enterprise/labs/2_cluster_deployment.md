# 2_cluster_deployment.md

## Usando el comando ```curl``` en el punto ```./api/v2/cm/deployment``` para desplegar la informaciòn del cluster

* Output

```
{
  "timestamp" : "2017-11-30T20:36:18.161Z",
  "clusters" : [ {
    "name" : "diegoalbertogh",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "enableSecurity",
          "value" : "true"
        } ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-2fe3648564532938e8cab79f7e72b0d0",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "b137b2c4-1de2-4261-9fc2-80f26d0fa980"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9k4ofckxlnjaha1f8z9vzzmdk"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-443f71ef47de8e2e799296f10baf3b82",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "c727eaf9-9314-4fe0-b130-f24093c12b67"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b7tw86dmvbkcx7q13juhy3zyd"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-57b1af5084d0da253af13378e14b3938",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "ad7a4b27-99df-4fe1-969c-f23c2e2b0dc1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4herfbnmissumzz45eix9d88a"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-10-1-2-236.ec2.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "Oozie_2017!"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-2fe3648564532938e8cab79f7e72b0d0",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "b137b2c4-1de2-4261-9fc2-80f26d0fa980"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1lekbbbyka2r8r7i7updkyghs"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-10-1-2-236.ec2.internal"
        }, {
          "name" : "database_password",
          "value" : "Hue_2017!"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-443f71ef47de8e2e799296f10baf3b82"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-57b1af5084d0da253af13378e14b3938",
        "type" : "HUE_LOAD_BALANCER",
        "hostRef" : {
          "hostId" : "ad7a4b27-99df-4fe1-969c-f23c2e2b0dc1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cvo8j1dyeqygxf647pezgfad9"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-443f71ef47de8e2e799296f10baf3b82",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "c727eaf9-9314-4fe0-b130-f24093c12b67"
        },
        "config" : {
          "items" : [ {
            "name" : "navmetadataserver_cmdb_password",
            "value" : "0d7820ee-7a06-4d98-b0d8-273548293c21"
          }, {
            "name" : "role_jceks_password",
            "value" : "2940uwz8c63i4njsbin4mbsvs"
          }, {
            "name" : "secret_key",
            "value" : "WLGVuHV8FEcslhJTzsEpqpnjAQxfgy"
          } ]
        }
      }, {
        "name" : "hue-KT_RENEWER-443f71ef47de8e2e799296f10baf3b82",
        "type" : "KT_RENEWER",
        "hostRef" : {
          "hostId" : "c727eaf9-9314-4fe0-b130-f24093c12b67"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "110i6l3ur5932pb3eafjg6ftz"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/disk1/dfs/dn,/disk2/dfs/dn"
          }, {
            "name" : "dfs_datanode_data_dir_perm",
            "value" : "700"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_http_port",
            "value" : "1006"
          }, {
            "name" : "dfs_datanode_port",
            "value" : "1004"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/extra2/dfs/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/disk1/dfs/nn,/disk2/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "3560964096"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/disk1/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "3560964096"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_encrypt_data_transfer_algorithm",
          "value" : "AES/CTR/NoPadding"
        }, {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "ASYPE4FmWAoEUeuqZL5e2resUjoYBs"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "0SA7nl1bdrcTyrkEhmlFUNi77CWnar"
        }, {
          "name" : "hadoop_security_authentication",
          "value" : "kerberos"
        }, {
          "name" : "hadoop_security_authorization",
          "value" : "true"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "thOm31UGLAoWsQ6GQDNuNTttifSj9y"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-443f71ef47de8e2e799296f10baf3b82",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "c727eaf9-9314-4fe0-b130-f24093c12b67"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-2fe3648564532938e8cab79f7e72b0d0",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "b137b2c4-1de2-4261-9fc2-80f26d0fa980"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "55r26xjhe6hplh4llwglzhhfy"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-443f71ef47de8e2e799296f10baf3b82",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "c727eaf9-9314-4fe0-b130-f24093c12b67"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "evxcr6c6u002epqmrb4awgwji"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-57b1af5084d0da253af13378e14b3938",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "ad7a4b27-99df-4fe1-969c-f23c2e2b0dc1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "do4hyl7i4kcijk36gloql5sig"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-2fe3648564532938e8cab79f7e72b0d0",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "b137b2c4-1de2-4261-9fc2-80f26d0fa980"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4gn3u4tzq7eii4nxkwfhxj36g"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-57b1af5084d0da253af13378e14b3938",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "ad7a4b27-99df-4fe1-969c-f23c2e2b0dc1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "banth0pnqzspcfnudv8c4hhci"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-443f71ef47de8e2e799296f10baf3b82",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "c727eaf9-9314-4fe0-b130-f24093c12b67"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4kzle8iohhoq646fdq4drkcfo"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-2fe3648564532938e8cab79f7e72b0d0",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "b137b2c4-1de2-4261-9fc2-80f26d0fa980"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6mwcew656w47y54msses705e4"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-443f71ef47de8e2e799296f10baf3b82",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "c727eaf9-9314-4fe0-b130-f24093c12b67"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "e3v1hbg19hue4h1otxwdccqv2"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-57b1af5084d0da253af13378e14b3938",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "ad7a4b27-99df-4fe1-969c-f23c2e2b0dc1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cn41awpjfb42nvbmbmbce1w4x"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-2fe3648564532938e8cab79f7e72b0d0",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "b137b2c4-1de2-4261-9fc2-80f26d0fa980"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "HdfsHAD"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "HdfsHAD"
          }, {
            "name" : "namenode_id",
            "value" : "41"
          }, {
            "name" : "role_jceks_password",
            "value" : "14zvizcow5whj3n4xuxs71rp"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-57b1af5084d0da253af13378e14b3938",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "ad7a4b27-99df-4fe1-969c-f23c2e2b0dc1"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "HdfsHAD"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "HdfsHAD"
          }, {
            "name" : "namenode_id",
            "value" : "51"
          }, {
            "name" : "role_jceks_password",
            "value" : "8q95em4yxbldtvnvxcct7nib8"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "12"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "3"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/disk1/yarn/nm,/disk2/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/disk1/yarn/container-logs,/disk2/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "7825"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "12989"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "8"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "MI5dClkwcKPFRJD2nmPcj1yV8iT5IF"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-443f71ef47de8e2e799296f10baf3b82",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "c727eaf9-9314-4fe0-b130-f24093c12b67"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1ye0py7wuwdmymtxb8hm2x0n8"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-2fe3648564532938e8cab79f7e72b0d0",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "b137b2c4-1de2-4261-9fc2-80f26d0fa980"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7pgl2upr8nrypi7w0ve1r2v4j"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-443f71ef47de8e2e799296f10baf3b82",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "c727eaf9-9314-4fe0-b130-f24093c12b67"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "lql95j7afhwjj019i3cf75zs"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-57b1af5084d0da253af13378e14b3938",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "ad7a4b27-99df-4fe1-969c-f23c2e2b0dc1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "xdmvkj57a6gfx18j99de9e44"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-2fe3648564532938e8cab79f7e72b0d0",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "b137b2c4-1de2-4261-9fc2-80f26d0fa980"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "47"
          }, {
            "name" : "role_jceks_password",
            "value" : "783s6v0ajf3der00imzh6v7xq"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "6311378944"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "631137894"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_enable_impersonation",
            "value" : "false"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "1967521792"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "331"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-10-1-2-236.ec2.internal"
        }, {
          "name" : "hive_metastore_database_name",
          "value" : "hive"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "Hive_2017!"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "sentry_service",
          "value" : "sentry"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-f8d4005394314a641b84772c25e012d6",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5b677344-f49c-4a18-a2cd-9770ecd4a28e"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-57b1af5084d0da253af13378e14b3938",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "ad7a4b27-99df-4fe1-969c-f23c2e2b0dc1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "awkixe85hmqog4yly88oer6df"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-f8d4005394314a641b84772c25e012d6",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "5b677344-f49c-4a18-a2cd-9770ecd4a28e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "hc5bjm7ylnuq9hew54dmd4qu"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "sentry",
      "type" : "SENTRY",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "sentry_server_database_host",
          "value" : "ip-10-1-2-209.ec2.internal"
        }, {
          "name" : "sentry_server_database_password",
          "value" : "Sentry_2017!"
        }, {
          "name" : "sentry_service_admin_group",
          "value" : "hive,impala,hue,solr,kafka,diegoalbertogh"
        }, {
          "name" : "sentry_service_allow_connect",
          "value" : "hive,impala,hue,hdfs,solr,kafka,diegoalbertogh"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "sentry-SENTRY_SERVER-2fe3648564532938e8cab79f7e72b0d0",
        "type" : "SENTRY_SERVER",
        "hostRef" : {
          "hostId" : "b137b2c4-1de2-4261-9fc2-80f26d0fa980"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6qklcjmz7iz2hyrvheypfm1yx"
          } ]
        }
      } ],
      "displayName" : "Sentry"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "5b677344-f49c-4a18-a2cd-9770ecd4a28e",
    "ipAddress" : "10.1.2.142",
    "hostname" : "ip-10-1-2-142.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "b137b2c4-1de2-4261-9fc2-80f26d0fa980",
    "ipAddress" : "10.1.2.208",
    "hostname" : "ip-10-1-2-208.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "c727eaf9-9314-4fe0-b130-f24093c12b67",
    "ipAddress" : "10.1.2.209",
    "hostname" : "ip-10-1-2-209.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "ad7a4b27-99df-4fe1-969c-f23c2e2b0dc1",
    "ipAddress" : "10.1.2.236",
    "hostname" : "ip-10-1-2-236.ec2.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__hue-HUE_SERVER-443f71ef47de8e2e799296f10baf3b82",
    "roles" : [ "ROLE_NAVIGATOR_ADMIN" ],
    "pwHash" : "658f94a0bd01341301fef3d2091cba94f59f83da735c5038831a38fff3a4ea99",
    "pwSalt" : -6118152590605792068,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-f8d4005394314a641b84772c25e012d6",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "d067e807809123e6f3a6866d55aaebdd49b65b2033b769561853abba068135b0",
    "pwSalt" : -64709424822176856,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-f8d4005394314a641b84772c25e012d6",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "bdc96c0c9864097734a975fbb6e4a0438629580039c52d6758ae76116e846050",
    "pwSalt" : 8210549581575023375,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-f8d4005394314a641b84772c25e012d6",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "e8fda8655ccb9898e8967e777983f11d84a14197ebfa38d8f68c7fddfa0cac74",
    "pwSalt" : -4655759071852001365,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-f8d4005394314a641b84772c25e012d6",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "26e4ea621c4da67207278d61ef55654805ee78321e611e1983819b6bd6b1ed8d",
    "pwSalt" : -9099226826978914781,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "39c3e26e31a6dc950d2f28f281d95c759b806e279e8680a01ca7ff414af47a17",
    "pwSalt" : 6885243503329601115,
    "pwLogin" : true
  }, {
    "name" : "diegoalbertogh",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "e43cd56fbdbc9b41219d487182c35b9b499d523ee89c52fa4dabab7fbdde68c6",
    "pwSalt" : 8106120327263309279,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "0ad6aa8c554bcedd8b3777c90ef42cc9b8085286bbdfeedbaf6672ec93ca0ea8",
    "pwSalt" : 987405593004238928,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.13.0",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20171002-1719",
    "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-10-1-2-236.ec2.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "reports"
        }, {
          "name" : "headlamp_database_password",
          "value" : "Reports_2017!"
        }, {
          "name" : "headlamp_database_user",
          "value" : "reports"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-f8d4005394314a641b84772c25e012d6",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "5b677344-f49c-4a18-a2cd-9770ecd4a28e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "67j7fbuhdr83i6k5n0ckwuf5y"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-f8d4005394314a641b84772c25e012d6",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "5b677344-f49c-4a18-a2cd-9770ecd4a28e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "df1cr2nkzwxh7hcxm6fdy9yrt"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-f8d4005394314a641b84772c25e012d6",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "5b677344-f49c-4a18-a2cd-9770ecd4a28e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "29x0p2pbk864b5vplooywh9yz"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-f8d4005394314a641b84772c25e012d6",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "5b677344-f49c-4a18-a2cd-9770ecd4a28e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "b6qrcolxhazeu2fiwy183ow9r"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-f8d4005394314a641b84772c25e012d6",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "5b677344-f49c-4a18-a2cd-9770ecd4a28e"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "af70v3o0rozygk4skimaqptfu"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "AD_USE_SIMPLE_AUTH",
      "value" : "false"
    }, {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/24/2012 17:20"
    }, {
      "name" : "KDC_ADMIN_HOST",
      "value" : "ip-10-1-2-209.ec2.internal"
    }, {
      "name" : "KDC_ADMIN_PASSWORD",
      "value" : "BQIAAAA7AAEACENMT1VERVJBAAxjbG91ZGVyYS1zY20AAAABWiA2QQEAFwAQ6Jf8GFkO8iQ3Th9kv9hVtQAAAAE="
    }, {
      "name" : "KDC_ADMIN_USER",
      "value" : "cloudera-scm@CLOUDERA"
    }, {
      "name" : "KDC_HOST",
      "value" : "ip-10-1-2-209.ec2.internal"
    }, {
      "name" : "KRB_MANAGE_KRB5_CONF",
      "value" : "true"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/5.12/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,http://archive.cloudera.com/kudu/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    }, {
      "name" : "SECURITY_REALM",
      "value" : "CLOUDERA"
    } ]
  }
}
```
