## MapReduce
### MapReduce过程
1. Map 映射
	- map函数将对每个元素根据特定标准映射，输出键值对
2. Shuffle (Group) 排序分组
	- 将所有键值对进行排序，并根据键值对中的键(key)进行分组，具有相同键的值会聚集在一起
3. Reduce 归约
	- reduce函数对每个键进值进行操作，将它们合并为更小的集合，reduce函数会收到(word, [1,2,3,...])形式的键值对，将值列表合并成单一的数字，例如全部相加。
### Partitioner 分区器
- 负责确定在shuffle阶段键值对应该发送给哪个reducer
- 一般情况下，分区器使用键的哈希值对reduce任务的数量取模决定reducer，用户可以自定义
- 需要确保相同的键被发送到同一个reducer
### Combiner 组合器
- 在map阶段将中间键值对合并，减少发送到reducer的键值对数量，提高效率
- 可以被看作是一个安放在map阶段的reducer
- Combiner的输出键值对必须和输入键值对有**相同的结构（键值类型）**
### 数据传输过程
1. Mapper：输入数据存储在分布式文件系统中。mapper从**本地磁盘**读取数据，处理他们，在**内存**中生成键值对并缓存。如果键值对过多，超出了可用的内存时，会被排序后写入**本地磁盘**。Mapper的输出会被**写入本地磁盘**
2. Combiner：从**本地磁盘**读取mapper的结果，处理数据的过程在**内存**中进行，输出会被写入到**本地磁盘**
3. Partitioner：发生在mapper节点上，从**本地磁盘**读取mapper或combiner的输出数据，在**内存**中处理数据，输出保存在**本地磁盘**
4. Shuffle：reducer节点会从mapper节点的**本地磁盘**中拉取自己需要的数据，通过网络发送。这些数据被保存在**内存**中，如果数据超出内存空间，则剩余的部分保存在**本地磁盘**
5. Reducer：如果未完成排序和合并，则这些操作会在**本地磁盘**进行。在内存中应用reduce函数生成输出。最后reducer的输出会被写回分布式文件系统中
### Secondary Sort
## NoSQL
### Broadcast (Map) Join

### Reduce-side (Common) Join

### Jaccard Similarity
- Jaccard Similarity
- Jaccard Distance
### Shingling
### Min-Hashing
### NoSQL Pros and Cons

### BASE and ACID

### NoSQL Types

### Consistency
- Strong consistency
- Eventual consistency
- Duplication (Denormalisation)

### Data Partitioning
- Table Partitioning
- Horizontal Partitioning
- Range Partition
- Hash Partition
- Consistent Hashing
### MongoDB
- Routers
- Config Server
- Replica Sets
- Replication


## Spark

## Streaming

## Graph

## Big Data System
