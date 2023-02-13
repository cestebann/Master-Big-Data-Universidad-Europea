What is Hadoop?


- Open-source project. 
- Open-source founded by David Cutting.
- It processes 
- Unexpensive computers. 
- Parallel processing, it operates on batch computing.
- Its response is not immediate (low latency)
- Not suitable for OTLP, OLAP, DSS. 
- It's not a replacement for relational databases. 

## What is big data?

Large collections of all kinds of data (structured, semi-structured and unstructured) that grows so large that it becomes difficult to manage the data in conventional ways. 

## Hadoop-related open source projects

- Eclipse: Popular ID donated by IBM.
- Lucene - text search engine library written in Java. 
- Hbase: Hadoop database. 
- Hive: Provides data warehouse tools, ETL, data and query data. 
- Pig: High level language that generate MapReduce code to analyze large datasets. 
- Spark: Cluster computing framework. 
- Zookeeper: Centralized configuration service
- Ambari: manages and monitors hadoop Cluster
- Avro
- UIMA
- Yarn
- MapReduce

## Hadoop is not for all typer of work

- Not to process transactions (random access)
- Not good wheen work cannot be parallelized
- not good for low latency data access
- not good for processing lots of small files
- not good for intensive calculations with little data.

## Big Data solutions and the Cloud

- Big data solutions are more than just Hadoop
    - Add BI analytics functionality
    - Derive information of data in motion
- Big Data solutions and the Clout are a perfect fit. 
    - The Cloud allows you to set up a cluster of systems in minutes and it's relatively inxpensive. 


# Hadoop architecture

## Key terms
- A **node** is simply a computer. This is typically
non-enterprise, commodity hardware for nodes that contain data.
- **A rack** is a collection of 30 or 40 nodes that are physically stored close together and are all connected to the same network switch.
- **Network bandwidth** between any two nodes in the same rack is greater than bandwidth between two nodes on different racks. You will see later how Hadoop takes advantage of this fact. 
A **Hadoop Cluster** (or just cluster from now on) is a collection of racks. 

## Pre Hadoop 2.2 Two main components
- Distributed File System
    - Hadoop Distributed File System (HDFS)
    - Ibm Spectrum Scale
- MapReduce Engine
    - Framework for peerforming calculations on the data in the file system
    - Has a built-in resource manager and scheduler. 

### HDFS

- HDFS runs on top of the existing file system. 
    - NOt POSIX compliant
    - Designed to tolerate high component failure rate. 
        - Reliability is through replication 
- Designed to handle very large files. he
larger the file, the less time Hadoop spends seeking for the next data location on disk, the more time Hadoop runs at the limit of the bandwidth of your disks. Seeks are generally expensive operations that are useful when they only need to analyze a small subset of your dataset. Since Hadoop is designed to run over your entire dataset, it is best to minimize seeks by using large files
    - Large streaming data access pattern 
        - No random access. Hadoop is designed for streaming or sequential data access rather than random access. Sequential data access means fewer seeks, since Hadoop only seeks to the beginning of each block and begins reading sequentially from there. Hadoop uses blocks to store a file or parts. 

#### HDFS file blocks

- A Hadoop block is a file on the underlying filesystem. Since the underlying filesystem stores files as blocks, one Hadoop block may consist of many blocks in the underlying file system. 
- Blocks are large. They default to 64 megabytes each and most systems run with block sizes of 128 megabytes or larger. 

Blocks have several advantages: 
- Firstly, they are fixed in size. This makes it easy to calculate how many can fit on a disk. 
- Secondly, by being made up of blocks that can be spread over multiple nodes, a file can be larger than any single disk in the cluster. 
- HDFS blocks also don't waste space. If a file is not an even multiple of the block size, the block containing the remainder does not occupy the space of an entire block. A  450 megabyte file with
a 128 megabyte block size consumes four blocks, but the fourth block does not consume a full 128 megabytes. 
- Finally, blocks fit well with replication, which allow HDFS to be fault tolerant and vailable on commodity hardware. 

#### MapReduce framework

- Hadoop's MapReduce is inspired by a paper Google published on the MapReduce technology.
- It is designed to process huge datasets for certain kinds of distributable problems using a large number of nodes. 
- A MapReduce program consists of two types of transformations that can be applied to data any number of times: a map transformation and a reduce transformation. 
- A MapReduce job is an executing MapReduce program that is divided into map tasks that run in parallel with each other and reduce tasks that run in parallel with each other.

#### Main types of nodes in pre-Hadoop 2.2. 

They are classified as HDFS or MapReduce V1 nodes. 
- For HDFS nodes we have the NameNode, and the DataNodes. 
- For MapReduce V1 nodes we have the JobTracker and the TaskTracker nodes.

There are other HDFS nodes such as the Secondary NameNode, Checkpoint node, and Backup node that are not discussed in this course. 
A client is shown as communicating with a JobTracker. It can also communicate with the NameNode and with any DataNode.
There is only one NameNode in the cluster. While the data that makes up a file is stored
in blocks at the data nodes, the metadata for a file is stored at the NameNode. The
NameNode is also responsible for the filesystem namespace. To compensate for the fact that
there is only one NameNode, one should configure the NameNode to write a copy of its state
information to multiple locations, such as a local disk and an NFS mount.
 If there is one node in the cluster to spend money on the best enterprise hardware for maximum reliability,
it is the NameNode. The NameNode should also have as much RAM as possible because it keeps
the entire filesystem metadata in memory.
A typical HDFS cluster has many DataNodes. DataNodes store the blocks of data and blocks
from different files can be stored on the same DataNode. When a client requests a file,
the client finds out from the NameNode which DataNodes stored the blocks that make up that
file and the client directly reads the blocks from the individual DataNodes. Each DataNode
also reports to the NameNode periodically with the list of blocks it stores. DataNodes
do not require expensive enterprise hardware or replication at the hardware layer. The
DataNodes are designed to run on commodity hardware and replication is provided at the
software layer.

A JobTracker node manages MapReduce V1 jobs. There is only one of these on the cluster.
It receives jobs submitted by clients. It schedules the Map tasks and Reduce tasks on
the appropriate TaskTrackers, that is where the data resides, in a rack-aware manner and
it monitors for any failing tasks that need to be rescheduled on a different
TaskTracker. To achieve the parallelism for your map and reduce tasks, there are many
TaskTrackers in a Hadoop cluster. Each TaskTracker spawns Java Virtual Machines to run your map
or reduce task. It communicates with the JobTracker and reads blocks from DataNodes.