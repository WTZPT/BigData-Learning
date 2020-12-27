# Spark快速大数据分析

## Spark数据分析导论

### Spark是什么

**Spark是一个用来实现快速而通用的集群计算平台。**

优点

- 计算速度快，扩展了广泛使用的MapReduce计算模型；能够在内存中进行计算
- 适用于各种各样原生需要多种不同的分布式平台场景，包括批处理、迭代算法、交互式查询、流处理。
- 提供丰富的接口，Python、Java、Scala和Sql,以及可以运行在Hadoop集群上，访问包括Cassandra在内的任意Hadoop数据源。

### 软件栈

![image-20201227124705841](Spark-%E5%BF%AB%E9%80%9F%E5%A4%A7%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90.assets/image-20201227124705841.png)

- Spark Core: 实现了Spark的基本功能，包含任务调度，内存管理，错误恢复，与存储系统交互模块等。还包含对**弹性分布式数据集（RDD）**的创建和操作API定义。RDD表示分布在多个计算节点上可以并行操作的元素集合，是Spark主要的编程抽象。

- Spark SQL: 用来操作结构化数据的程序包。

- Spark Streaming:对实时数据进行流式计算的组件。

- MLlib: 提供常见的机器学习（ML）功能的程序库。MLlib提供多种机器学习算法,包括分类，回归，聚类，协同过滤等，还提供支持模型评估，数据导入等额外的支持功能。

- GraghX: 操作图的程序库，提供并行的图计算。

- 集群管理器：Spark支持在各种集群管理器（Cluster manager)上运行，包括Hadoop YARN、Apache Mesos,以及Spark自带的简易调度器，叫做独立调度器。

  

## Spark入门

### Spark开发环境搭建

- Spark 1.6.2 - Scala 2.10

  https://www.scala-lang.org/download/2.10.5.html

- Spark 2.0.0 - Scala 2.11

  https://www.scala-lang.org/download/2.11.0.html

### 读取本地文件

![image-20201227152436746](Spark-%E5%BF%AB%E9%80%9F%E5%A4%A7%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90.assets/image-20201227152436746.png)

### 第一个基于Scala的Spark程序

单词计数：

![image-20201227155658954](Spark-%E5%BF%AB%E9%80%9F%E5%A4%A7%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90.assets/image-20201227155658954.png)

### Spark核心概念

#### 在集群上运行Spark

![image-20201227172320747](Spark-%E5%BF%AB%E9%80%9F%E5%A4%A7%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90.assets/image-20201227172320747.png)

 Driver Program是通过SparkContext对象访问spark。
SparkContext对象代表对一个计算集群的连接。有SparkContext，就可以用它来创建RDD。
在Shell中SparkContext在启动时自动创建好了，叫作sc. 

#### 分片

 每个分片包含一部分数据，partitions可在集群的不同节点上计算。
分片是spark并行执行的单元，spark是顺序的，并行的处理分片。 



## RDD编程

