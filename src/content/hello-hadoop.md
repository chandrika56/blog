---
layout: post
title: 'Hello Hadoop | Learn Hadoop in just a few minutes easily!'
author: Chandrika
tags: ['Big Data']
image: img/hello-hadoop.jpg
date: '2020-06-05T23:46:37.121Z'
draft: false
---

> Follow me on Dev.to at dev.to/chandrika56

In this Article (Click to skip to that topic):

- [Hadoop: Whats the buzz around it?](#what-is-yaml)
- [Hadoop EcoSystem ](#draw)
- [HDFS: Hadoop Distributed File System](#blur)
- [YARN: Yet Another Resource Negotiator ](#yarn)
- [MapReduce: Mappers and Reducers](#map)
- [Pig : A fast and easy alternative to MapReduce](#pig)
- [TEZ](#tez)
- [Hive](#hive)
- [Ambari: UI](#ambari)
- [Mesos: An Alternative to YARN](#mesos)
- [Spark: Queen of Hadoop Chessboard](#spark)

- [HBase](#hbase)
- [Apache STORM](#storm)
- [OOZIE](#oozie)
- [ZooKeeper](#zoo)
- [Data Ingestion: Sqoop + Flume + Kafka](#kafka)
- [External Data Storages: MySQL, Cassandra, MongoDB](#storage)
- [Query Engines: Drill + Hue + Phoenix + Presto + Zeplin](#query)

`Platform:` Hortonworks Sandbox

<h2 id='what-is-yaml'> Hadoop: Whats the buzz around it?</h2>
<br/>

> Hadoop is an open source software platform with utilities or tools, for distributed storage and distributed processing on very large files and datasets, performed on several computer

I agree if it doesnt make complete sense yet. Lets break it down.

_Example:_ Lets say we got employee information of millions of people working in Google, Amazon , Facebook and we have to combine all their information and remake the list in decreasing order of salary.

To load such big data into one normal computer and perform operations on it, making the computer to process each every employee, will either make computer to burst out like a SpaceX rocket or take a lo...ng time to process that our next generation have to see the output!

If we alloted this data to several computers, each computer processing a small piece of it, it gives fast output without the overload of processing huge data.

This is what Hadoop does,

_distributed storage_-The huge data is distributed to several computers and is stored there.

_distributed processing_-Instead of one costly computer with high processing power, several normal computers can process the big data.

In short, Hadoop has tools to store, process this big data giving us the expected results.

_Lets see how exactly Big Data is handled in Hadoop!_

<h2 id='draw'> Hadoop EcoSystem</h2>

Hadoop has many components, each has its own purpose and functions.(_Kind of like each hero in Endgame has their own movie_.)

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/av65p9uw5foyeeq0ywop.png)

HDFS, YARN and MapReduce belong to core Hadoop Ecosystem while others were added later on to solve specific problems. Lets explore each one of them, one by one.

Lets say we have a huge chunks of potato(Big data) with us and we wish to make French fries, Chips and Nuggets.

1.  In order to make them, we divide potato into 3 blocks of potato for french fries, potato for chips and nuggets,
    which is what `HDFS` does, dividing the big chunk of data and distribute to several computers.

2.  All resources or ingrediants required for each dish are alloted respectively, similiar to `YARN` which manages the resources needed for each chunk or cluster.

3.  We transform this potato to the desired dish which is same as `MapReducers` which transform data in efficient manner and aggregate the data giving us the desired result.

Lets explore in more detail about each component.

<h2 id='blur'> HDFS: Hadoop Distributed File System</h2>
 
 As it says, it distributes the big file across many computers as follows:

- The big file is converted to blocks(each block size max upto 128 Mb)

- Blocks are stored across many computers.

- _Redundancy_:To handle failure of one computer, more than one copy of each block is stored in each computer. So that if one fails,other computers will have, failed computer's data.

<h2 id='yarn'> YARN: Yet Another Resource Negotiator</h2>

- Its the heartbeat of the hadoop system, all the _data processing_ happens here.
- It provides the computational resources like CPUs, memory, etc for application executions.
- It does job scheduling and manages the resources like what nodes are available for, which ones should be allowed to run tasks etc.
- Usually, its advised not to code against YARN directly. Instead, use one of the higher-level tools, for example Hive, to make your life easier.

In a way, like how Operating System allots resources to a computer, YARN `allocates resources` in Hadoop.

<h2 id='map'> MapReduce: Mappers and Reducers</h2>

So we got data in HDFS, resources allocated from YARN. Now how to make get our desired results from this? We code using MapReduce.

MapReduce has two functions: Mappers and Reducers.
Here python or java programming is used to code those functions.Its overall, a programming model to process and compute across the data.

- Mappers split the data and map them according to the desired output.
- Reducers take the output of the mappers and aggregate or combine the data to give result.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/ynx62ganu3vxhfb87d9w.jpg)

As input gets in, mapper transforms data one by one and organizes according to the output we desire.

The reducer, reduces the mapper output to the aggregated form which we require as output.

<h2 id='pig'> Pig : A fast and easy alternative to MapReduce</h2> 
 
 - Pig Latin, `a scripting language`, uses SQL like syntax, forming relationship, selecting a data, filtering it, transforming it etc. Contains `User defined functions` to help us create our own functions.
 - Not all business problems can be solved by converting to mappers and reducers form. So Pig Latin sitting on top of MapReduce, converts our Pig Latin script into map reduce form.
 - Pig script can be run by either of the 3 below:
    
     - Grunt(Command Line Interpreter)
     - Script(place the script in file and running it)
     - Ambari (Directly from Pig View)

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/1fasv0zk1lt2ac77xgfk.jpg)

 <h2 id='tez'> TEZ</h2> 
 
 - We might wonder if using pig on top of mapreduce might increase latency. Tez is present in between them, to optimize and make it 10x faster.

- It makes Hive, Pig and Map Reduce jobs faster, optimising physical dataflow and resource usage.
- Using DAG(Directed Acyclic Graphs) it sees the workflow of the jobs and finds the optimal way among it making our job easier.

Suppose:we have three ways, 1-2-3 , 4-9-8, 2-7-9 and we need to find the smallest path, we choose 1-2-3. DAG works in somewhat similar way.

- The output is processed again and again Through DAG giving us the optimal solution.

<h2 id='hive'> Hive</h2>

- It takes `SQL queries` as input from command prompt and transforms them to mapreduce jobs and automatically gets the job done.
- We can store the result of query into a `view`, perform a query onto entire cluster and `define our own functions`.
- Though Pig and Hive might be similiar,Hive is used for completely structured Data whereas Pig Hadoop Component is used for semi structured data.

- Pig is relatively faster than Hive.
- Hive is slow and not useful for realtime transactions unlike Pig and Spark.
- It might give the feel of a relational database, but it cant delete, insert etc as there are no tables, joins, primary keys and the data is just a flat text, `de-normalized`.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/3590hkz2m4fi8hiaytcy.png)

As you can observe,the queries used are same as SQL queries.

<h2 id='ambari'> Ambari: UI</h2> 
 
 - Its pretty much a web interface to graphically interact with the cluster and its usage.
 - It gives us a high-level view of your cluster, what’s running, what system you are using, what resources are available/in use.
 -  It shows statistics about the cluster like CPU Usage,Memory Usage,Network Usage, Cluster load etc.
 - All services like HDFS, YARN etc can be used on a cluster using Ambari.
 - Even Hadoop can be installed using Ambari.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/lyi1oetwh9ear07yxkio.png)

<h2 id='mesos'> Mesos: An Alternative to YARN</h2>

- Its simliar to YARN but then difference is Mesos is more general.
- In simple words, YARN works only on Hadoop components like mapreduce etc where as Mesos can allcate resources to outside of hadoop like web servers.

- YARN is for analytical and long process jobs where as Mesos is for both long and short process jobs.

<h2 id='spark'> Spark: Queen of Hadoop Chessboard</h2>

- Spark engine is pretty fast, infact 100x faster than mapreduce and is used for large scale data processing.
- Like Hive -> it can handle SQL queries, like Apache STORM ->it handles real time streaming hence we call it the queen.
- Processing in Spark happens in this way:

  - `Driver Program`, containing script to control what happens in the job.
  - `Cluster Manager`,which can be YARN, Mesos or its own Spark Cluster Manager.
  - `Executor`, it contains cache prioritizing memory based solution unlike other disk based solutions.

  ![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/629c95m8ig8xd24xi3g1.png)

  Spark has many components:

  - Spark Streaming: Handles Realtime data.
  - Spark SQL: SQL interface, takes SQL queries.
  - MLLib: Machine Learning operations can be performed without about mappers and reducers to solve a problem.
  - GraphX: All graph related problems and analytics are done using this.
  - Spark Core: It provides distributed task dispatching, scheduling, and basic I/O functionalities.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/g9ymdncgm68w3lw4wcm1.jpg)

Spark uses a specialized fundamental data structure known as `RDD (Resilient Distributed Datasets)`.Its an object representing dataset and we can perform operations on that object just like in java.

<h2 id='hbase'> HBase</h2>

- Its basically a scalable `NoSQL Database`.
- A columnar data storage, pretty fast and finds it useful for high data transaction rates.
- CRUD(Create,Read,Update and Delete) operations are employed here.

<h2 id='storm'> Apache STORM</h2>

- Processes continuous `realtime streaming data` like from sensors or weblogs etc.
- Even spark streaming does this but more in batch intervals but storm handles data event wise.
- Spout is the term used for sources of the streaming data i.e., they produce. Bolts is the term used for those which transform or aggregate this streaming data.
- Usually kafka(which sends data into cluster) and storm are used as a pair.

   <h2 id='oozie'> OOZIE</h2>

- Runs and Schedules various jobs/tasks on Hadoop.

- Instructions are given via XML file.

 <h2 id='zoo'> ZooKeeper</h2>
  
  - Co-ordinates everything on cluster. Like which is the master node, task assigned for each worker node, which node is up and which is down and which worker nodes are available etc.
  - If a master node dies, it chooses who the next master should be. 
  
  _Example_:This phenomenon can be observed in whatsapp groups or in videocalls where if the host leaves the group, someone else is assigned as the next host.

> Outside Hadoop EcoSystem, we can have databases to store the data and Query Engines to get input data to the cluster. Lets have a look at them!

   <h2 id='kafka'> Data Ingestion: Sqoop + Flume + Kafka</h2> 
 So how do you get data into the cluster? Sqoop,Flume and Kafka help with this via data ingestion.

_Sqoop_: Sqoop is a command-line interface application tool for transferring data between relational database servers and Hadoop.

- Its just a way of tying hadoop database to relational database.

_Flume_: Another way of sending data into cluster and it acts as a buffer between the data coming in and storing, so that cluster wont go down with overwhelming data coming in realtime.

_Kafka_: This is more a general publisher/subscriber model where the `publishers` send/produce data as `topics` which are subscribed by `consumers`.

- Collects any sort of data from PCs, webservers etc and broadcast it into Hadoop Cluster.

<h2 id='storage'> External Data Storages: MySQL, Cassandra, MongoDB</h2>

_MySQL:_ Typical `SQL` based relational database.

_Cassandra :_ Its a `NoSQL` columnar database with no single point of failure. It favours availability and partial- tolerance in CAP theorem.

_MongoDB :_ A `NoSQL` database which uses document model. Its used when we deal with huge data and its pretty flexible.

![Alt Text](https://dev-to-uploads.s3.amazonaws.com/i/1txw10ipyzg1k0uyq1iv.png)

   <h2 id='query'> Query Engines: Drill + Hue + Phoenix + Presto + Zeplin</h2> 
  
All these are interactive query engines to fetch required data from databases under them like Hbase, Cassandra etc.

- `Drill` lets us use SQL queries, even when the databases under it (Hbase, Cassandra, MongoDB etc) are non relational Databases.

- `Phoenix` is similar to drill with SQL queries but with ACID properties(Atomicity,Consistency,Isolation and Durability).Its fast but works only HBase.

- `Presto` is similar to Drill and unlike Drill, it connects to Cassandra and executes query across the cluster.

- `Hue` (Hadoop User Experience), an SQL Cloud Editor, is used for query and as UI in Cloudera just like Ambari to HortonWorks.

- `Zeppelin` has Notebook UI to visualize the data similar to jupyter notebooks for TensorFlow and share, interact with the code.

It might be overwhelming to see many components doing the same work.Ultimately based on the task and the type of database(whether its relational or non structered data etc) and other factors, we need to decide the right component and utilize it and it comes with knowledge of the components,practice and experience.

Hope you had fun learning Hadoop, i for one certainly had fun sharing about it!!

> Follow me on Dev.to at dev.to/chandrika56
> <br/>

> Now you can follow us to explore more interesting topics, in Instagram at: **@code_voyager**

Great to have you here, lets get back for the next post and explore more!

Have an amazing day!
