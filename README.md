# cp-kafka-cli-commands

Q. Cheking underreplicated partitions from kafka broker host:
A.
    /usr/bin/kafka-topics --bootstrap-server < kafka broker host >:9091  --describe --under-replicated-partitions --command-config /etc/kafka/client.properties

Q1. How to check status ZK status?
A: use 4 letter commands:
to validate if zookeeper service is healthy or not:
<pre><code>
    echo stat | nc <zookeeper ip> 2181
    echo mntr | nc <zookeeper ip> 2181
    echo isro  | nc <zookeeper ip> 2181
<code><pre>
A: Don't forget to allow ZOO_4LW_COMMANDS_WHITELIST="*" or lesser e.g. "stat", if you're running Zk in a Container. Otherwise you'll get a stat is not executed because it is not in the whitelist.

A: Go to bin directory of Zookeeper and type
<pre><code>
    ./zkServer.sh status
<code><pre>

A:
<pre><code>
    jps -l | grep zookeeper
<code><pre>
or even like this:
<pre><code>
    jps | grep Quorum
<code><pre>

A:
<pre><code>
    echo "ruok" | nc localhost 2181 ; echo 
<code><pre>
  expected response: imok
