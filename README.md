# Kafka
Kafka
# **Kafka**
>Apache Kafka is a software platform which is based on a distributed streaming process. It is a publish-subscribe messaging system which let exchanging of data between applications, servers, and processors as well

* It was originally developed by LinkedIn, and later it was donated to the Apache Software Foundation.
* Written in Java and Scala
* Support for several clients like C++, Python, Ruby, Go, .Net, Nodejs, etc.
* Mainly used for real time data pipeline, real time streaming applications.
### **Messaging System**
>A messaging system is a simple exchange of messages between two or more persons, devices, etc. A publish-subscribe messaging system allows a sender to send/write the message and a receiver to read that message. In Apache Kafka, a sender is known as a producer who publishes messages, and a receiver is known as a consumer who consumes that message by subscribing it.

#### **Stream Processing**
>Stream processing is the processing of data in motion, or in other words, computing on data directly as it is produced or received.


#### **Why Kafka**
* Kafka is not designed to be a task queue. There are other tools that are better for such use cases, for example, RabbitMQ. If you need a database, use a database, not Kafka. Kafka is not good for long-term storage

##### **Kafka Architecture**
![Kafka Arch](https://data-flair.training/blogs/wp-content/uploads/sites/2/2018/04/Kafka-Architecture.png)

_Brokers_ - A Kafka cluster is comprised of one or more servers which are known as brokers or Kafka brokers.
 A broker is a container that holds several topics with their multiple partitions. The brokers in the cluster are identified by an integer id only.
 ![Broker](https://static.javatpoint.com/tutorial/kafka/images/kafka-topics-2.png)
 
 _Zookeepr_ - manages the broker, external to kafak cluster
 
 Topics_ - is similar to a table in db and refer to a particular stream of data.In Kafka, we can create n number of topics as we want.
  It is identified by its name, a producer publishes data to the topics, and a consumer reads that data from the topic by subscribing it.
Name of a topic is unique across kafka cluster.
![Topics](https://static.javatpoint.com/tutorial/kafka/images/kafka-topics.png)

_Message_ - A kafka record pertaining to a topic.
* Consists of key-value pair and a metadata. key is optional. Here value is the actual record.
* No specific data type . Simple bytes or Strings..
* Messages produced for a topic are identified by an offset number(integer)
* Metadata - headers, timestamp, topic name, partition no, rtc
![Message](https://cdn.confluent.io/wp-content/uploads/Apache_Kafka_NYSE_Sample_Architecture-1024x468.png)
![Message](https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2020/12/15/selfhosted12.png)

_Partitions_ - A topic is split into several parts which are known as the partitions of the topic. While creating a topic, we need to specify the number of partitions(the number is arbitrary and can be changed later)
Each message gets stored into partitions with an incremental id known as its Offset value. The order of the offset value is guaranteed within the partition only and not across the partition.
 The offsets for a partition are infinite.
* The data once written to a partition can never be changed. It is immutable. The offset value always remains in an incremental state, it never goes back to an empty space.
 Also, the data is kept in a partition for a limited time only.
* Unit of storage
* Unlimited scaling
* Records in a partition stored in order of arrival
* Topic Creation - no of partitions, replication factor, retention period(def 7 days)
* Replication factor should be less than or equal to no of brokers
* Writes to Leader partition, one of the follower becomes leader when the broker containing the partition fails
 
 *replica id is same as the broker id
 
#### Apache Kafka Core  Api's
1. _Producer API_: This API allows/permits an application to publish streams of records to one or more topics. (discussed in later section)

2. _Consumer API_: This API allows an application to subscribe one or more topics and process the stream of records produced to them.

3. _Streams API_: This API allows an application to effectively transform the input streams to the output streams. It permits an application to act as a stream processor which consumes an input stream from one or more topics, and produce an output stream to one or more output topics.

4. _Connector API_: This API executes the reusable producer and consumer APIs with the existing data systems or application

_

 



 
