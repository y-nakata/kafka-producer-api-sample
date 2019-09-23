# kafka-producer-api-sample
See https://kafka.apache.org/documentation/#producerapi and 
https://kafka.apache.org/23/javadoc/index.html?org/apache/kafka/clients/producer/KafkaProducer.html

# kafka server/topic operations memo

----
```
cd \kafka_2.12-2.3.0
start bin\windows\zookeeper-server-start.bat config\zookeeper.properties

bin\windows\kafka-topics.bat --create --bootstrap-server localhost:9092 --replication-factor 3 --config min.insync.replicas=2 --partitions 1 --topic my-topic
```
----
```
cd \kafka_2.12-2.3.0
start bin\windows\kafka-server-start.bat config\server.properties
start bin\windows\kafka-server-start.bat config\server-1.properties
start bin\windows\kafka-server-start.bat config\server-2.properties

bin\windows\kafka-topics.bat --describe --bootstrap-server localhost:9092 --topic my-replicated-topic

bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic my-topic --from-beginning
```
