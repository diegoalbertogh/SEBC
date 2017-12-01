# 1_terasort_tests.md

## Realizar prueba HDFS throughput

* Output TERAGEN

```
[diegoalbertogh@ip-10-1-2-133 ~]$ time hadoop jar /opt/cloudera/parcels/CDH-5.12.1-1.cdh5.12.1.p0.3/jars/hadoop-examples.jar teragen -D dfs.block.size=33554432 -D mapreduce.job.maps=4 107374182 /user/diegoalbertogh/teragen-out
17/11/28 23:59:11 INFO client.RMProxy: Connecting to ResourceManager at ip-10-1-2-199.ec2.internal/10.1.2.199:8032
17/11/28 23:59:11 INFO terasort.TeraGen: Generating 107374182 using 4
17/11/28 23:59:12 INFO mapreduce.JobSubmitter: number of splits:4
17/11/28 23:59:12 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/11/28 23:59:12 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511930378552_0001
17/11/28 23:59:12 INFO impl.YarnClientImpl: Submitted application application_1511930378552_0001
17/11/28 23:59:12 INFO mapreduce.Job: The url to track the job: http://ip-10-1-2-199.ec2.internal:8088/proxy/application_1511930378552_0001/
17/11/28 23:59:12 INFO mapreduce.Job: Running job: job_1511930378552_0001
17/11/28 23:59:19 INFO mapreduce.Job: Job job_1511930378552_0001 running in uber mode : false
17/11/28 23:59:19 INFO mapreduce.Job:  map 0% reduce 0%
17/11/28 23:59:39 INFO mapreduce.Job:  map 13% reduce 0%
17/11/28 23:59:45 INFO mapreduce.Job:  map 17% reduce 0%
17/11/28 23:59:51 INFO mapreduce.Job:  map 20% reduce 0%
17/11/28 23:59:57 INFO mapreduce.Job:  map 24% reduce 0%
17/11/29 00:00:03 INFO mapreduce.Job:  map 27% reduce 0%
17/11/29 00:00:09 INFO mapreduce.Job:  map 28% reduce 0%
17/11/29 00:00:15 INFO mapreduce.Job:  map 30% reduce 0%
17/11/29 00:00:21 INFO mapreduce.Job:  map 33% reduce 0%
17/11/29 00:00:27 INFO mapreduce.Job:  map 37% reduce 0%
17/11/29 00:00:33 INFO mapreduce.Job:  map 43% reduce 0%
17/11/29 00:00:39 INFO mapreduce.Job:  map 47% reduce 0%
17/11/29 00:00:45 INFO mapreduce.Job:  map 51% reduce 0%
17/11/29 00:00:51 INFO mapreduce.Job:  map 54% reduce 0%
17/11/29 00:00:57 INFO mapreduce.Job:  map 57% reduce 0%
17/11/29 00:01:03 INFO mapreduce.Job:  map 62% reduce 0%
17/11/29 00:01:09 INFO mapreduce.Job:  map 65% reduce 0%
17/11/29 00:01:15 INFO mapreduce.Job:  map 68% reduce 0%
17/11/29 00:01:21 INFO mapreduce.Job:  map 71% reduce 0%
17/11/29 00:01:27 INFO mapreduce.Job:  map 75% reduce 0%
17/11/29 00:01:34 INFO mapreduce.Job:  map 77% reduce 0%
17/11/29 00:01:40 INFO mapreduce.Job:  map 82% reduce 0%
17/11/29 00:01:46 INFO mapreduce.Job:  map 86% reduce 0%
17/11/29 00:01:52 INFO mapreduce.Job:  map 89% reduce 0%
17/11/29 00:01:58 INFO mapreduce.Job:  map 92% reduce 0%
17/11/29 00:02:04 INFO mapreduce.Job:  map 96% reduce 0%
17/11/29 00:02:10 INFO mapreduce.Job:  map 99% reduce 0%
17/11/29 00:02:16 INFO mapreduce.Job:  map 100% reduce 0%
17/11/29 00:02:16 INFO mapreduce.Job: Job job_1511930378552_0001 completed successfully
17/11/29 00:02:17 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=581496
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=344
                HDFS: Number of bytes written=10737418200
                HDFS: Number of read operations=16
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=8
        Job Counters
                Launched map tasks=4
                Other local map tasks=4
                Total time spent by all maps in occupied slots (ms)=687314
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=687314
                Total vcore-milliseconds taken by all map tasks=687314
                Total megabyte-milliseconds taken by all map tasks=703809536
        Map-Reduce Framework
                Map input records=107374182
                Map output records=107374182
                Input split bytes=344
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1170
                CPU time spent (ms)=148750
                Physical memory (bytes) snapshot=715063296
                Virtual memory (bytes) snapshot=6393327616
                Total committed heap usage (bytes)=1551368192
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=230593859918397906
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=10737418200

real    3m8.095s
user    0m5.477s
sys     0m0.353s

```

* Output TERASORT

```
[diegoalbertogh@ip-10-1-2-133 ~]$ time hadoop jar /opt/cloudera/parcels/CDH-5.12.1-1.cdh5.12.1.p0.3/jars/hadoop-examples.jar terasort /user/diegoalbertogh/teragen-out /user/diegoalbertogh/terasort-out
17/11/29 00:07:56 INFO terasort.TeraSort: starting
17/11/29 00:07:58 INFO input.FileInputFormat: Total input paths to process : 4
Spent 252ms computing base-splits.
Spent 7ms computing TeraScheduler splits.
Computing input splits took 260ms
Sampling 10 splits of 320
Making 12 from 100000 sampled records
Computing parititions took 602ms
Spent 864ms computing partitions.
17/11/29 00:07:58 INFO client.RMProxy: Connecting to ResourceManager at ip-10-1-2-199.ec2.internal/10.1.2.199:8032
17/11/29 00:07:59 INFO mapreduce.JobSubmitter: number of splits:320
17/11/29 00:07:59 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1511930378552_0002
17/11/29 00:07:59 INFO impl.YarnClientImpl: Submitted application application_1511930378552_0002
17/11/29 00:07:59 INFO mapreduce.Job: The url to track the job: http://ip-10-1-2-199.ec2.internal:8088/proxy/application_1511930378552_0002/
17/11/29 00:07:59 INFO mapreduce.Job: Running job: job_1511930378552_0002
17/11/29 00:08:05 INFO mapreduce.Job: Job job_1511930378552_0002 running in uber mode : false
17/11/29 00:08:05 INFO mapreduce.Job:  map 0% reduce 0%
17/11/29 00:08:13 INFO mapreduce.Job:  map 1% reduce 0%
17/11/29 00:08:19 INFO mapreduce.Job:  map 3% reduce 0%
17/11/29 00:08:21 INFO mapreduce.Job:  map 4% reduce 0%
17/11/29 00:08:22 INFO mapreduce.Job:  map 6% reduce 0%
17/11/29 00:08:26 INFO mapreduce.Job:  map 7% reduce 0%
17/11/29 00:08:33 INFO mapreduce.Job:  map 9% reduce 0%
17/11/29 00:08:34 INFO mapreduce.Job:  map 10% reduce 0%
17/11/29 00:08:35 INFO mapreduce.Job:  map 11% reduce 0%
17/11/29 00:08:36 INFO mapreduce.Job:  map 13% reduce 0%
17/11/29 00:08:45 INFO mapreduce.Job:  map 14% reduce 0%
17/11/29 00:08:46 INFO mapreduce.Job:  map 16% reduce 0%
17/11/29 00:08:47 INFO mapreduce.Job:  map 17% reduce 0%
17/11/29 00:08:49 INFO mapreduce.Job:  map 18% reduce 0%
17/11/29 00:08:50 INFO mapreduce.Job:  map 19% reduce 0%
17/11/29 00:08:56 INFO mapreduce.Job:  map 20% reduce 0%
17/11/29 00:08:59 INFO mapreduce.Job:  map 22% reduce 0%
17/11/29 00:09:00 INFO mapreduce.Job:  map 23% reduce 0%
17/11/29 00:09:03 INFO mapreduce.Job:  map 25% reduce 0%
17/11/29 00:09:04 INFO mapreduce.Job:  map 26% reduce 0%
17/11/29 00:09:12 INFO mapreduce.Job:  map 28% reduce 0%
17/11/29 00:09:13 INFO mapreduce.Job:  map 29% reduce 0%
17/11/29 00:09:14 INFO mapreduce.Job:  map 30% reduce 0%
17/11/29 00:09:17 INFO mapreduce.Job:  map 32% reduce 0%
17/11/29 00:09:24 INFO mapreduce.Job:  map 33% reduce 0%
17/11/29 00:09:25 INFO mapreduce.Job:  map 34% reduce 0%
17/11/29 00:09:26 INFO mapreduce.Job:  map 36% reduce 0%
17/11/29 00:09:30 INFO mapreduce.Job:  map 38% reduce 0%
17/11/29 00:09:34 INFO mapreduce.Job:  map 39% reduce 0%
17/11/29 00:09:37 INFO mapreduce.Job:  map 40% reduce 0%
17/11/29 00:09:38 INFO mapreduce.Job:  map 41% reduce 0%
17/11/29 00:09:39 INFO mapreduce.Job:  map 42% reduce 0%
17/11/29 00:09:40 INFO mapreduce.Job:  map 43% reduce 0%
17/11/29 00:09:44 INFO mapreduce.Job:  map 44% reduce 0%
17/11/29 00:09:45 INFO mapreduce.Job:  map 45% reduce 0%
17/11/29 00:09:49 INFO mapreduce.Job:  map 46% reduce 0%
17/11/29 00:09:51 INFO mapreduce.Job:  map 48% reduce 0%
17/11/29 00:09:54 INFO mapreduce.Job:  map 49% reduce 0%
17/11/29 00:09:57 INFO mapreduce.Job:  map 50% reduce 0%
17/11/29 00:09:59 INFO mapreduce.Job:  map 51% reduce 0%
17/11/29 00:10:02 INFO mapreduce.Job:  map 52% reduce 0%
17/11/29 00:10:04 INFO mapreduce.Job:  map 53% reduce 0%
17/11/29 00:10:05 INFO mapreduce.Job:  map 55% reduce 0%
17/11/29 00:10:11 INFO mapreduce.Job:  map 56% reduce 0%
17/11/29 00:10:12 INFO mapreduce.Job:  map 57% reduce 0%
17/11/29 00:10:15 INFO mapreduce.Job:  map 58% reduce 0%
17/11/29 00:10:17 INFO mapreduce.Job:  map 59% reduce 0%
17/11/29 00:10:18 INFO mapreduce.Job:  map 60% reduce 0%
17/11/29 00:10:19 INFO mapreduce.Job:  map 61% reduce 0%
17/11/29 00:10:20 INFO mapreduce.Job:  map 62% reduce 0%
17/11/29 00:10:24 INFO mapreduce.Job:  map 63% reduce 0%
17/11/29 00:10:27 INFO mapreduce.Job:  map 64% reduce 0%
17/11/29 00:10:28 INFO mapreduce.Job:  map 65% reduce 0%
17/11/29 00:10:31 INFO mapreduce.Job:  map 67% reduce 0%
17/11/29 00:10:32 INFO mapreduce.Job:  map 68% reduce 0%
17/11/29 00:10:38 INFO mapreduce.Job:  map 70% reduce 0%
17/11/29 00:10:40 INFO mapreduce.Job:  map 71% reduce 0%
17/11/29 00:10:43 INFO mapreduce.Job:  map 72% reduce 0%
17/11/29 00:10:44 INFO mapreduce.Job:  map 73% reduce 0%
17/11/29 00:10:45 INFO mapreduce.Job:  map 74% reduce 0%
17/11/29 00:10:50 INFO mapreduce.Job:  map 75% reduce 0%
17/11/29 00:10:51 INFO mapreduce.Job:  map 76% reduce 0%
17/11/29 00:10:52 INFO mapreduce.Job:  map 77% reduce 0%
17/11/29 00:10:56 INFO mapreduce.Job:  map 78% reduce 0%
17/11/29 00:10:57 INFO mapreduce.Job:  map 80% reduce 0%
17/11/29 00:10:59 INFO mapreduce.Job:  map 81% reduce 0%
17/11/29 00:11:03 INFO mapreduce.Job:  map 82% reduce 0%
17/11/29 00:11:05 INFO mapreduce.Job:  map 83% reduce 0%
17/11/29 00:11:07 INFO mapreduce.Job:  map 84% reduce 0%
17/11/29 00:11:09 INFO mapreduce.Job:  map 85% reduce 0%
17/11/29 00:11:11 INFO mapreduce.Job:  map 86% reduce 0%
17/11/29 00:11:14 INFO mapreduce.Job:  map 87% reduce 0%
17/11/29 00:11:18 INFO mapreduce.Job:  map 87% reduce 2%
17/11/29 00:11:21 INFO mapreduce.Job:  map 87% reduce 5%
17/11/29 00:11:22 INFO mapreduce.Job:  map 87% reduce 6%
17/11/29 00:11:25 INFO mapreduce.Job:  map 88% reduce 6%
17/11/29 00:11:26 INFO mapreduce.Job:  map 88% reduce 9%
17/11/29 00:11:27 INFO mapreduce.Job:  map 89% reduce 16%
17/11/29 00:11:28 INFO mapreduce.Job:  map 89% reduce 17%
17/11/29 00:11:29 INFO mapreduce.Job:  map 89% reduce 24%
17/11/29 00:11:30 INFO mapreduce.Job:  map 89% reduce 27%
17/11/29 00:11:36 INFO mapreduce.Job:  map 90% reduce 27%
17/11/29 00:11:37 INFO mapreduce.Job:  map 91% reduce 27%
17/11/29 00:11:40 INFO mapreduce.Job:  map 91% reduce 28%
17/11/29 00:11:45 INFO mapreduce.Job:  map 92% reduce 28%
17/11/29 00:11:46 INFO mapreduce.Job:  map 93% reduce 28%
17/11/29 00:11:52 INFO mapreduce.Job:  map 94% reduce 28%
17/11/29 00:11:53 INFO mapreduce.Job:  map 94% reduce 29%
17/11/29 00:11:57 INFO mapreduce.Job:  map 95% reduce 29%
17/11/29 00:11:59 INFO mapreduce.Job:  map 96% reduce 29%
17/11/29 00:12:05 INFO mapreduce.Job:  map 97% reduce 29%
17/11/29 00:12:08 INFO mapreduce.Job:  map 98% reduce 29%
17/11/29 00:12:09 INFO mapreduce.Job:  map 98% reduce 30%
17/11/29 00:12:12 INFO mapreduce.Job:  map 99% reduce 30%
17/11/29 00:12:17 INFO mapreduce.Job:  map 100% reduce 30%
17/11/29 00:12:18 INFO mapreduce.Job:  map 100% reduce 31%
17/11/29 00:12:20 INFO mapreduce.Job:  map 100% reduce 33%
17/11/29 00:12:21 INFO mapreduce.Job:  map 100% reduce 44%
17/11/29 00:12:22 INFO mapreduce.Job:  map 100% reduce 47%
17/11/29 00:12:23 INFO mapreduce.Job:  map 100% reduce 57%
17/11/29 00:12:24 INFO mapreduce.Job:  map 100% reduce 64%
17/11/29 00:12:26 INFO mapreduce.Job:  map 100% reduce 70%
17/11/29 00:12:27 INFO mapreduce.Job:  map 100% reduce 73%
17/11/29 00:12:28 INFO mapreduce.Job:  map 100% reduce 74%
17/11/29 00:12:29 INFO mapreduce.Job:  map 100% reduce 80%
17/11/29 00:12:30 INFO mapreduce.Job:  map 100% reduce 81%
17/11/29 00:12:32 INFO mapreduce.Job:  map 100% reduce 84%
17/11/29 00:12:33 INFO mapreduce.Job:  map 100% reduce 86%
17/11/29 00:12:35 INFO mapreduce.Job:  map 100% reduce 87%
17/11/29 00:12:38 INFO mapreduce.Job:  map 100% reduce 89%
17/11/29 00:12:39 INFO mapreduce.Job:  map 100% reduce 90%
17/11/29 00:12:41 INFO mapreduce.Job:  map 100% reduce 91%
17/11/29 00:12:44 INFO mapreduce.Job:  map 100% reduce 92%
17/11/29 00:12:45 INFO mapreduce.Job:  map 100% reduce 94%
17/11/29 00:12:46 INFO mapreduce.Job:  map 100% reduce 95%
17/11/29 00:12:48 INFO mapreduce.Job:  map 100% reduce 96%
17/11/29 00:12:50 INFO mapreduce.Job:  map 100% reduce 97%
17/11/29 00:12:51 INFO mapreduce.Job:  map 100% reduce 99%
17/11/29 00:12:52 INFO mapreduce.Job:  map 100% reduce 100%
17/11/29 00:12:53 INFO mapreduce.Job: Job job_1511930378552_0002 completed successfully
17/11/29 00:12:53 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=4769084447
                FILE: Number of bytes written=9480890389
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=10737465560
                HDFS: Number of bytes written=10737418200
                HDFS: Number of read operations=996
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=24
        Job Counters
                Launched map tasks=320
                Launched reduce tasks=12
                Data-local map tasks=320
                Total time spent by all maps in occupied slots (ms)=3339395
                Total time spent by all reduces in occupied slots (ms)=1102917
                Total time spent by all map tasks (ms)=3339395
                Total time spent by all reduce tasks (ms)=1102917
                Total vcore-milliseconds taken by all map tasks=3339395
                Total vcore-milliseconds taken by all reduce tasks=1102917
                Total megabyte-milliseconds taken by all map tasks=3419540480
                Total megabyte-milliseconds taken by all reduce tasks=1129387008
        Map-Reduce Framework
                Map input records=107374182
                Map output records=107374182
                Map output bytes=10952166564
                Map output materialized bytes=4662963282
                Input split bytes=47360
                Combine input records=0
                Combine output records=0
                Reduce input groups=107374182
                Reduce shuffle bytes=4662963282
                Reduce input records=107374182
                Reduce output records=107374182
                Spilled Records=214748364
                Shuffled Maps =3840
                Failed Shuffles=0
                Merged Map outputs=3840
                GC time elapsed (ms)=41551
                CPU time spent (ms)=1703040
                Physical memory (bytes) snapshot=175910776832
                Virtual memory (bytes) snapshot=532508573696
                Total committed heap usage (bytes)=173085294592
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10737418200
        File Output Format Counters
                Bytes Written=10737418200
17/11/29 00:12:53 INFO terasort.TeraSort: done

real    4m57.491s
user    0m8.474s
sys     0m0.389s

```

## Tiempos

* Para TERAGEN 3m8.095s
* Para TERASORT 4m57.491s
