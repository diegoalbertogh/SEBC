# 0_replication.md

## Visualizar el nodo del cluster de un compañero y relizar una copia

* Output
```
[centos@ip-10-1-2-133 ~]$ hdfs fsck /user/centos/target/ -files -blocks
Connecting to namenode via http://ip-10-1-2-199.ec2.internal:50070/fsck?ugi=centos&files=1&blocks=1&path=%2Fuser%2Fcentos%2Ftarget
FSCK started by centos (auth:SIMPLE) from /10.1.2.133 for path /user/centos/target at Wed Nov 29 01:10:26 CST 2017
/user/centos/target <dir>
/user/centos/target/source <dir>
/user/centos/target/source/alexis <dir>
/user/centos/target/source/alexis/_SUCCESS 0 bytes, 0 block(s):  OK

/user/centos/target/source/alexis/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-354167033-10.1.2.199-1511930332811:blk_1073744069_3245 len=134217728 Live_repl=3
1. BP-354167033-10.1.2.199-1511930332811:blk_1073744072_3248 len=127926272 Live_repl=3

/user/centos/target/source/alexis/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-354167033-10.1.2.199-1511930332811:blk_1073744066_3242 len=134217728 Live_repl=3
1. BP-354167033-10.1.2.199-1511930332811:blk_1073744071_3247 len=127926272 Live_repl=3

/user/centos/target/source/hugo <dir>
/user/centos/target/source/hugo/_SUCCESS 0 bytes, 0 block(s):  OK

/user/centos/target/source/hugo/part-m-00000 262144000 bytes, 2 block(s):  OK
0. BP-354167033-10.1.2.199-1511930332811:blk_1073744127_3303 len=134217728 Live_repl=3
1. BP-354167033-10.1.2.199-1511930332811:blk_1073744130_3306 len=127926272 Live_repl=3

/user/centos/target/source/hugo/part-m-00001 262144000 bytes, 2 block(s):  OK
0. BP-354167033-10.1.2.199-1511930332811:blk_1073744128_3304 len=134217728 Live_repl=3
1. BP-354167033-10.1.2.199-1511930332811:blk_1073744131_3307 len=127926272 Live_repl=3

Status: HEALTHY
 Total size:    1048576000 B
 Total dirs:    4
 Total files:   6
 Total symlinks:                0
 Total blocks (validated):      8 (avg. block size 131072000 B)
 Minimally replicated blocks:   8 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Wed Nov 29 01:10:26 CST 2017 in 3 milliseconds


The filesystem under path '/user/centos/target' is HEALTHY
```
