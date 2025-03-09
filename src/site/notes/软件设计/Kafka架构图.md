---
{"dg-publish":true,"permalink":"/软件设计/Kafka架构图/","noteIcon":"default"}
---



在系统架构设计中特别提及Kafka，是因为它在现代分布式系统中扮演着**异步消息解耦**的核心角色。以下是[[软件设计/Kafka架构图\|Kafka架构图]]的关键解析：

### 核心架构组成
1. **Producer/Consumer** 
- <mark style="background: #BBFABBA6;">生产者</mark>通过$p(t)=hash(key)\ \%\ partitions$算法路由到不同Partition
- <mark style="background: #BBFABBA6;">消费者</mark>组实现`pub-sub`模式（见![[Consumer Group示意图\|Consumer Group示意图]]


====
1. **Broker集群**
- 采用ZooKeeper协调（新版用KRaft协议替代）
- 数据分片存储：`Topic = Partition_0 + Partition_1 + ...`
- 副本机制：==Leader-Follower==<!--什么是副本机制-->结构（参考[[软件设计/副本同步机制\|副本同步机制]]）

1. **持久化设计**
- 顺序写磁盘：$O(1)$时间复杂度
- 分段日志：`.log` + `.index` + `.timeindex`
- ==零拷贝技术==<!--什么意思-->：`sendfile()`

### 为什么重要？
1. **流量削峰**  
   百万级TPS处理能力（比较传统MQ如RabbitMQ仅万级）

2. **事件溯源支持**  
   可作为==事件驱动架构==<!--！！！-->的「中枢神经」（见[[Event Sourcing模式\|Event Sourcing模式]]）

3. **流批统一**  
   与Flink/Spark集成实现实时计算（参考[[流处理架构\|流处理架构]]）

需要我展开说明Kafka与其他消息队列（如RabbitMQ/Pulsar）的架构对比吗？或是具体应用场景示例？