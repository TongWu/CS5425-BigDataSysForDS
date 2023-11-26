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
在MapReduce框架中，数据是以键值对(key-value pairs)的形式进行处理的。在这个过程中，Map阶段生成的键值对会被分组(grouped)和排序(sorted)，然后传递给Reduce阶段。默认情况下，MapReduce只会按键（key）进行排序，这称为“自然排序”。
如果我们需要以一种额外的方式对值进行排序，则这被称作为二次排序"secondary sort":
- 定义一个新的“复合键”（composite key），格式为(K1, K2)，其中K1是原始键（也称为“自然键”），K2是我们希望用于排序的变量。在这种情况下，复合键将会影响如何对数据进行分区和排序：
	- **Partitioner**: 需要自定义分区器，使其仅按K1进行分区，而不是按复合键(K1, K2)分区。这样可以保证相同的K1会被发送到同一个reducer，但是在reducer内部，数据会根据K2的值进行排序。
这样，每个reducer接收的数据就会首先根据K1分组，然后在每个组内根据K2排序，实现了二次排序的目的
## NoSQL
### Broadcast (Map) Join
1. **选择较小的数据集**：在两个需要连接的数据集中，选择较小的那个进行广播。这意味着这个数据集会被发送到集群中的每个节点，以便于本地连接操作。
2. **广播到所有节点**：所选择的较小数据集会被复制并广播到集群中的每个节点。在Spark中，这通常通过`broadcast`函数实现。
3. **本地连接**：大数据集不动，较小的数据集被广播到每个节点后，大数据集的每个分区会与本地节点上的小数据集进行连接操作。由于小数据集已经在每个节点的内存中，这大大减少了网络传输的需求，并且可以并行地在每个节点上快速完成连接。
4. **减少数据洗牌**：使用broadcast join 可以避免在网络中进行昂贵的数据洗牌操作，因为只有小数据集在节点间移动，而大数据集则保持静止。
### Reduce-side (Common) Join
Reduce side join 是在 MapReduce 编程模型中用于处理大规模数据集连接的一种机制。这种类型的 join 操作涉及到 Map 和 Reduce 两个阶段，在这个过程中，两个数据集都参与到数据的洗牌和排序过程中。这种 join 在处理两个大数据集的连接时尤其有用，因为它不需要将整个数据集加载到内存中。
以下是 Reduce side join 的基本步骤：
1. **Map 阶段**：
    - 两个数据集（比如数据集A和数据集B）都会被读取，并在 Map 阶段被处理。
    - Map 函数会对每条记录产生中间的键值对（key-value pairs）。键通常是两个数据集中用于连接的共同字段，而值则是包含原始数据和数据来源标识（例如来自数据集A或B）的记录。
2. **Shuffle 阶段**：
    - Shuffle 过程将 Map 输出的中间键值对根据键进行排序和分组。所有共同键的值都会被集中到一起。
3. **Reduce 阶段**：
    
    - 在 Reduce 阶段，每个 Reduce 任务接收到了包含相同键的所有值的列表。这个列表中会同时包含来自数据集A和B的记录。
    - Reduce 函数然后遍历这些值，根据键值对中的标识将来自数据集A和B的记录分开，并执行连接操作。
    - 连接后的结果会被写出到最终的输出文件中。

Reduce side join 在处理大型分布式数据集时非常强大，但也有其缺点。它需要大量的数据在网络中移动（即数据洗牌），这可能会导致较高的网络传输开销，并且如果连接的键有很多重复值，也可能会在 Reduce 阶段产生瓶颈。
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
