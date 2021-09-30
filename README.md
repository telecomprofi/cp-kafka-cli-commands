# cp-kafka-cli-commands

Q. Cheking underreplicated partitions from kafka broker host:
A.
    /usr/bin/kafka-topics --bootstrap-server < kafka broker host >:9091  --describe --under-replicated-partitions --command-config /etc/kafka/client.properties

Q1. How to check status ZK status?
A: use 4 letter commands:
to validate if zookeeper service is healthy or not
    echo stat | nc <zookeeper ip> 2181
    echo mntr | nc <zookeeper ip> 2181
    echo isro  | nc <zookeeper ip> 2181

A: Don't forget to allow ZOO_4LW_COMMANDS_WHITELIST="*" or lesser e.g. "stat", if you're running Zk in a Container. Otherwise you'll get a stat is not executed because it is not in the whitelist.

A: Go to bin directory of Zookeeper and type
    ./zkServer.sh status


A:
    jps -l | grep zookeeper
or even like this:
    jps | grep Quorum


A:
    echo "ruok" | nc localhost 2181 ; echo 
  expected response: imok
