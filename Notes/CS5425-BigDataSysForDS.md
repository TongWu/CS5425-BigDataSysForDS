# 1 - Introduction of Big Data and Data Science

## 1.1 What will we learn?

- We will learn to **process different types of data**:
  - Large data volume
  - Graph data
  - Stream data (infinite/never-ending)

- We will learn to **use different model of computation**:
  - MapReduce / Spark
  - Large graph processing engines
  - Streams and online algorithms

## 1.2 Data Science

> Data science is an **interdisciplinary** field about processes and systems to extract **knowledge or insights** from data in various forms.

![image-20231009161750553](https://images.wu.engineer/images/2023/10/09/image-20231009161750553.png)

## 1.3 Challenges of Big Data: the 4 ‘V’s

![image-20231009161828669](https://images.wu.engineer/images/2023/10/09/image-20231009161828669.png)

> “大数据”的挑战经常用“四大V”来描述，这四个V分别是：
>
> 1. **Volume（容量）**: 大数据首先是“大”的，代表的是数据的量。随着互联网、物联网、社交媒体和企业交易等数据源的增加，数据的量也在快速增长。这对存储、处理和分析这些数据带来了挑战。企业需要有能力在合理的时间内处理这些数据，并从中获取有价值的信息。
> 2. **Velocity（速度）**: 这是数据产生和处理的速度。在今天的数字化时代，数据几乎是实时生成的，这要求系统能够实时或近实时地捕获、处理和响应这些数据。例如，社交媒体帖子、金融交易、在线互动等都需要快速的数据处理。
> 3. **Variety（多样性）**: 数据来自多种不同的来源，并且有各种不同的格式。这包括结构化数据（如数据库中的表格数据）、半结构化数据（如JSON、XML文件）和非结构化数据（如文本、图片、视频等）。整合、清洗和分析这些不同类型的数据是一个巨大的挑战。
> 4. **Veracity（真实性）**: 这是关于数据的质量和准确性的问题。不是所有的数据都是完美和准确的，有时数据可能是不完整的、误导的或含有噪声。确保数据的真实性对于从中获得有价值的洞察非常重要。
>
> 随着大数据技术的发展，一些人也提到了其他的“V”字，如“Value（价值）”（从大数据中提取的实际价值）和“Vulnerability（脆弱性）”（数据的安全性和隐私问题）。但传统的四大V仍然是描述大数据挑战的主要方式。

## 1.4 Cloud Computing

### Utility Computing

- Computing resources as a metered service (pay as you go)
- Ability to dynamically provision virtual machines

### Virtualization and Containers

![image-20231009162113286](https://images.wu.engineer/images/2023/10/09/image-20231009162113286.png)

- Virtual Machines: Enable sharing of hardware resources by running each application in an isolated VM
  - **High overhead** as each VM has its own OS
- Containers: enable lightweight sharing of resources, as applications run in an isolated way, but still share the same OS.
  - A container is a **lightweight software package** that encapsulates an application and its enviornment

### Everything as a Service

- Infrastructure as a Service (IaaS): Utility Computing
  - Example: Amazon EC2, Rackspace, Google Compute Engine
- Platform as a Service (PaaS)
  - Provides hosting from web applications and takes care of the hardware maintenance, upgrades…
  - Example: Google App Engine
- Software as a Service (SaaS)
  - Example: Gmail, Dropbox, Zoom

> IaaS、PaaS 和 SaaS 是云计算服务的三种基本模式，每种模式都有其独特的特点和用途。以下是对这三种模式的简要解释：
>
> 1. **IaaS (Infrastructure as a Service 基础设施即服务)**
>    - **描述**：IaaS 提供了虚拟化的计算资源作为服务。这意味着用户可以租用物理硬件上的虚拟化部分，如服务器、存储和网络。
>    - **用途**：适用于需要完全控制其基础设施但又不希望投资物理硬件的企业。
>    - **示例**：Amazon EC2、Google Compute Engine、Microsoft Azure Virtual Machines。
>    - **用户控制范围**：操作系统、存储、已部署的应用程序和可能的有限网络组件（例如防火墙、负载均衡器）。
> 2. **PaaS (Platform as a Service 平台即服务)**
>    - **描述**：PaaS 提供了一个平台，允许用户开发、运行和管理应用程序，而无需处理基础设施的复杂性。
>    - **用途**：适用于开发人员，他们只想关注编写代码而不是基础设施管理。
>    - **示例**：Google App Engine、Microsoft Azure App Services、Heroku。
>    - **用户控制范围**：应用程序和数据。
> 3. **SaaS (Software as a Service 软件即服务)**
>    - **描述**：SaaS 提供了通过互联网访问的应用程序。在这种模式下，软件应用程序和其相关的数据都托管在云中。
>    - **用途**：适用于终端用户，他们只需使用应用程序而不必担心基础设施或平台的管理。
>    - **示例**：Google Workspace、Microsoft Office 365、Salesforce。
>    - **用户控制范围**：通常限于用户界面和特定的应用程序设置。
>
> 总结起来，从 IaaS 到 PaaS 再到 SaaS，用户对底层资源的直接控制逐渐减少，但同时管理的复杂性也大大减少，使用户可以更加专注于自己的核心业务或任务。

## 1.5 Data Centers

### **Storage Hierarchy**

![image-20231009162636821](https://images.wu.engineer/images/2023/10/09/image-20231009162636821.png)

### Bandwidth vs Latency

- **Bandwidth**: maximum amount of data that can be transmitted per unit time (e.g. in GB/s) 

- **Latency**: time taken for 1 packet to go from source to destination (*one-way*) or from source to destination back to source (*round trip),* e.g. in ms

- When transmitting a *large* amount of data, bandwidth tells us roughly how long the transmission will take.

- When transmitting a very *small* amount of data, latency tells us how much delay there will be. 

- **Throughput** is similar to bandwidth, but instead of referring to capacity, it refers to the rate at which some data was *actually transmitted* across the network during some period of time.

### Capacity of Storage Hierarchy

![image-20231009162735730](https://images.wu.engineer/images/2023/10/09/image-20231009162735730.png)

1. **Disk has much higher capacity than DRAM**

2. **Storage hierarchy**: *capacity* increases as we go from Local Server, to Rack, to Datacenter. 

3. **Disk reads are much more expensive than DRAM**, both in terms of with **higher latency** and **lower bandwidth**. 

4. **Costs increase over the storage hierarchy**: **latency increases** as we go from Local to Rack to Datacenter.

5. **Costs increase over the storage hierarchy**: **bandwidth decreases** as we go from Local to Rack to Datacenter.

### Price-Speed Tradeoff

![image-20231009162919834](https://images.wu.engineer/images/2023/10/09/image-20231009162919834.png)

# 2 - MapReduce

## 2.1 Motivation

### **Typical Big Data Problem**

- Iterate over a large number of records
- Extract something of interest from each (Map)
- Shuffle and sort intermediate results (Shuffle)
- Aggregate intermediate results (Reduce)
- Generate final output

**Example: **Tabulating Election Results from Multiple Polling Sites

- Image you are hired to develop the software for election counting system
- You need to aggregate vote counts from multiple stations into the final counts

![image-20231009163723903](https://images.wu.engineer/images/2023/10/09/image-20231009163723903.png)

**`MapReduce`**

![image-20231009163916693](https://images.wu.engineer/images/2023/10/09/image-20231009163916693.png)

> MapReduce 是一种编程模型和数据处理方法，用于处理和生成大数据集。目的是为了简化在大型、分布式环境中的数据处理。MapReduce 主要由两个步骤组成：Map（映射）步骤和 Reduce（归约）步骤。
>
> 1. **Map步骤**：
>
> - 输入数据被分割成小的数据块，并行地由多个任务（或称为节点）进行处理。
> - 每个 Mapper 任务处理其所分配的数据块，并输出一组键值对。
> - 例如，一个简单的 Map 任务可能会处理文本数据并输出每个单词及其出现的次数（键是单词，值是1）。
>
> 2. Shuffle
>
> - Shuffle 主要涉及的是数据的组织与重新分配。
>
> - **数据组织**：当 Map 任务执行完毕后，每个 Mapper 输出的是一系列的键值对。在 Shuffle 阶段，这些键值对需要根据其键进行排序。
>
> - **数据传输**：在 Shuffle 过程中，系统还负责将排序后的键值对传输到合适的 Reducer 节点上。这通常涉及跨网络的数据移动，因为在一个分布式系统中，Map 任务和 Reduce 任务可能不在同一台机器上执行。
>
> - **数据分组**：Shuffle 还包括一个分组步骤，其中键值对被按键分组，以便每个 Reducer 可以接收到一组具有相同键的键值对。这意味着每个 Reducer 会处理一个特定的键集。
>
> 3. **Reduce步骤**：
>    - 这一步在 Map 步骤之后进行。Reducer 接收到所有 Mapper 输出的键值对。
>    - 键值对会根据键进行排序和分组，这样所有相同的键都会聚集在一起。
>    - 每个 Reducer 任务都会处理一组共享相同键的键值对，并输出一个新的键和其相关的值。
>    - 继续上面的例子，Reducer 会接收到所有包含相同单词的键值对，然后将这些值加起来，输出单词及其总出现次数。
>
> MapReduce 的优点是它可以很容易地进行横向扩展，因为 Map 和 Reduce 任务都是并行处理的。这使得 MapReduce 适合于运行在成百上千的机器上，处理 TB 或 PB 级别的数据。

### Writing `MapReduce` Programs

- Typical Interface: Programmers specify two functions:
  - `map(k1, v1) -> List(k2, v2)`
  - `reduce(k2, list(v2)) -> List(k3, v3)`
  - All values with the same key are sent to the same reducer

![image-20231009164416969](https://images.wu.engineer/images/2023/10/09/image-20231009164416969.png)

### `MapReduce` Execution Framework

- Handles scheduling
  - Assigns workers to map and reduce tasks
- Handles ‘Data Distribution’
  - Move processes to data
- Handles synchronization
  - Gathers, sorts, and shuffles intermediate data
- Handles errors and faults
  - Detects worker failures and restarts

## 2.2 Basic `MapReduce`

![image-20231009210228985](https://images.wu.engineer/images/2023/10/09/image-20231009210228985.png)

### (1) Submit

User submits MapReduce program (including code for the map and reduce functions) and configurations  (eg. number of workers) to Master Node.

### (2) Schedule

Master schedules resources for map and reduce tasks (Note: Master does not handle any actual data)

### (3) Read

Input files are separated into ‘splits’ of around 128MB each. Each split corresponds to one map task. Workers execute map task 1 at a time.

### Map Phase

Each worker iterates over each `<key, value>` tuple in its input split, and computes the map function on each tuple

### (4) Local Write

Each worker writes the outputs of the map function to intermediate files on its own local disk. These files are partitioned by key (i.e. all the data for a single key is in one partition)

### (5) Remote Read

Each reduce worker is responsible for 1 or more keys. For each such key, it reads the data it needs from the corresponding partition of each mapper’s local disk.

### Reduce Phase

After receiving all the needed key value pairs, it computes the reduce function

### (6) Write

The output of the reduce function is written (usually to HDFS, a distributed file system)

### Shuffle Phase

The shuffle phase is comprised of the local write and remote read steps. Thus, it happens partly on the map workers, and partly on the reduce workers.

Shuffle阶段包括本地写入和远程读取步骤。因此，它部分发生在 map 处理程序上，部分发生在 reduce 处理程序上。

> 1. **提交任务**：
>    - 用户程序首先向 Master 节点提交 MapReduce 任务（标记为 `(1) submit`）。
> 2. **任务调度**：
>    - Master 节点接收到任务后开始调度工作。它将 Map 任务和 Reduce 任务分配给可用的 Worker 节点。
>      - 标记为 `(2) schedule map` 的箭头表示 Master 节点指派 Map 任务给 Worker 节点。
>      - 标记为 `(2) schedule reduce` 的箭头表示 Master 节点指派 Reduce 任务给 Worker 节点。
> 3. **Map阶段**：
>    - 输入数据被分为多个分片，例如 "split 0", "split 1" 等。
>    - Worker 节点开始读取它们分配的数据分片，如标记 `(3) read`。
>    - Map 任务处理读取的数据，并为每个数据项生成键值对。
>    - 处理后的数据被写入本地磁盘作为中间文件，如标记 `(4) local write`。
> 4. **Shuffle阶段**：
>    - 在 Map 任务和 Reduce 任务之间，有一个被标记为 "Shuffle phase" 的过程。
>    - 在此阶段，中间文件的数据被重新组织并传输给合适的 Reduce Worker。这通常涉及网络传输，因为需要的数据可能存在于不同的 Worker 节点上。
>    - 这个过程中的数据读取被标记为 `(5) remote read`。
> 5. **Reduce阶段**：
>    - Reduce Worker 节点现在开始处理它们收到的数据。它们将具有相同键的所有值组合在一起并进行归约。
>    - 归约的结果被写入输出文件，如标记 `(6) write`。在此示例中，有两个输出文件 "output file 0" 和 "output file 1"。

Q: What disadvantages are these if the size of each split (or chunk) is too big or small?

A: Too big: limited parallelism. Too small: high overhead (master node may be overwhelmed by scheduling work)

> 1. 太大的分片：
>    - **限制的并行性**：如果分片太大，那么在一个给定时间内可并行处理的分片数量将会减少。这意味着你可能有大量的计算资源处于空闲状态，因为它们必须等待其他较大的分片处理完毕。这样，你就没有充分利用集群的并行处理能力。
> 2. 太小的分片：
>    - **高开销**：太小的分片意味着系统中会有大量的分片需要处理。这导致初始化、调度和管理这些分片的开销变得很大。
>    - **主节点可能被压垮**：在 MapReduce 中，主节点（或 Master 节点）负责调度和跟踪所有的 Map 和 Reduce 任务。如果有大量的小分片，主节点可能会被大量的调度工作压垮，因为它需要跟踪和管理这些任务的状态，这会影响整体的性能。
>
> 选择一个合适的分片大小是一种平衡：太大的分片可能限制并行性并延长作业的完成时间，而太小的分片可能增加系统的开销并对主节点造成压力。在实际应用中，需要根据具体的数据和计算需求来确定最佳的分片大小。

### Definition of Map Task, Mapper, Map Function

- Worker
  - A worker is a component of the cluster that performs storage and processing tasks (you can loosely think of it as a physical machine)
- Map Task:
  - Map Task is a basic unit of work; it is typically 128MB. At the beginning the input is broken into splits of 128MB. A map task is a job requiring to process one split; not a worker.
  - A Single worker can handle multiple map tasks. Typically, when a worker completes a map task (eg. split 0). it is re-assigned to another task (eg. split 3)
- A ‘mapper’ or ‘reducer’ will generally refer to the process executing a map or reduce task, not to physical machines/workers.
  - E.g. in this diagram there are 5 map tasks, and thus 5 mappers, but only 3 workers.
- “Map Function” is a single call to the user-defined `map(k1,v1) -> List(k2,v2)` function.
  - Note that a single map task can involve many calls to such a map function: e.g. within a 128MB split, there will often be many (key, value) pairs, each of which will produce one call to a map function.
- Barrier between map and reduce phases
  - Necessary, otherwise the reduce phase might compute the wrong answer
  - Note that the shuffle phase can begin copying intermediate data earlier
- If a reduce task handles multiple keys, it will process these keys in sorted order

## 2.3 Partitioner and Combiner

- Programmers specify two functions:

  - **map** (k1, v1) → List(k2, v2)

  - **reduce** (k2, List(v2)) → List(k3, v3)

  - All values with the same key are reduced together

- The execution framework handles everything else…

- Not quite… Usually, programmers **optionally** also specify **partition**, and **combine** functions
  - These are an optional optimization to reduce network traffic

### Partitioner

![image-20231009164416969](https://images.wu.engineer/images/2023/10/09/image-20231009164416969.png)

- Note that key A went to reducer 1, and key B went to reducer 2
- By default, the assignment of keys to reducers is determined by a hash function
  - e.g. key `k` goes to reducer `(hash(k) % num_reducers)`

![image-20231009230327705](https://images.wu.engineer/images/2023/10/09/image-20231009230327705.png)

- User can optionally implement a custom partition, e.g. to better spread out the load among reducers (if some keys have much more values than others)

> **Partitioner（分区器）**:
>
> - **作用**：Partitioner 负责确定中间键值对应该发送到哪个 Reduce 任务。在 Shuffle 阶段，Partitioner 根据中间键值对的键来决定它们应该分配给哪个 Reducer。
> - **默认行为**：在许多 MapReduce 实现中（例如 Hadoop），默认的 Partitioner 使用键的哈希值对 Reduce 任务的数量取模来决定目标 Reducer。但用户也可以自定义 Partitioner 以满足特定的需求。
> - **重要性**：正确的分区策略确保相同的键都被发送到同一个 Reducer，这是 MapReduce 编程模型的核心假设。

### Combiner

![image-20231009230543152](https://images.wu.engineer/images/2023/10/09/image-20231009230543152.png)

- Combiners locally aggregate output from mappers
- Combiners are ‘mini-reducers’: in this example, combiners and reducers are the same function

### Correctness of Combiner

- It is user’s responsibility to ensure that the combiner does not affect the correctness of the final output, whether the combiners runs 0, 1, or multiple times
  - Example: in election example, the combiner and reducer are a ‘sum’ over values with the same key. Summing can be done in any order without affecting correctness:
    - e.g. sum(sum(1,1), 1, sum(1,1,1)) = sum(1,1,1,1,1,1) = 6
  - The same holds for `max` and `min`, but not same for `means` and `minus`
  - In general, it is correct to use reducers as combiners if the reduction involves a binary operation
    - Associative: `a+(b+c) = (a+b)+c`
    - Commutative: `a + b = b + a`

## 2.4 Examples

### Performance Guidelines for Basic Algorithmic Design

- **Linear scalability:** more nodes can do more work in the same time

  - Linear on data size

  - Linear on computer resources

- **Minimize disk and network I/O**

  - Minimize disk I/O; sequential vs. random.

  - Minimize network I/O; send data in bulk vs in small chunks

- **Reduce memory working set** of each task/worker

  - ”Working set” = portion of memory that is actively being used during algorithm execution

  - Large working set -> high memory requirements / probability of out-of-memory errors. 

- Guidelines are applicable to Hadoop, Spark, …

> 为了使算法在大数据环境中（如 Hadoop、Spark 等框架）高效运行，设计时需要考虑以下性能方面的建议：
>
> 1. **线性可扩展性**：
>    - 无论是从数据大小还是计算资源（如 CPU、节点数等）来看，算法的性能应随着资源的增加线性地提高。
>    - 这意味着，如果我们增加更多的节点或更多的计算资源，我们应该期望算法在相同的时间内完成更多的工作。
> 2. **最小化磁盘和网络I/O**：
>    - 磁盘I/O（输入/输出）尤其是随机I/O，通常是计算任务中的性能瓶颈。因此，最好尽可能地减少磁盘I/O，优先选择顺序读写而不是随机读写。
>    - 对于网络I/O，传输大块的数据通常比传输小块的数据更有效率。因此，尽可能地以批量方式发送数据，以减少网络传输的次数和开销。
> 3. **减少每个任务/工作节点的内存工作集**：
>    - “工作集”是指算法执行期间正在活跃使用的内存部分。
>    - 一个大的工作集意味着算法需要更多的内存来运行，这可能会导致更高的内存要求或者出现内存不足的错误。
> 4. **通用性**：
>    - 这些建议不仅适用于一个特定的框架，而是广泛适用于许多大数据处理框架，如 Hadoop、Spark 等。
>
> 总的来说，这些指导原则强调了在设计算法时要考虑到资源的有效使用，从而确保算法在大数据环境中的高效性能。

### Word Count

```python
class Mapper {
	def map(key: Long, value: Text) = {
		for (word <- tokenize(value)) {
			emit(word, 1)
		}
	}
}

class Reducer {
	def reduce(key: Text, values: Iterable[Int]) = {
		for (value <- values) {
			sum += value
		}
		emit(key, sum)
	}
}
```

This mapper processes each word one by one, and emits a “1”, to be summed by the reducers.

> 1. **Mapper 类**：
>    - **功能**：Mapper 的任务是将输入文本数据分解为单词，并为每个单词输出一个键值对。键是单词本身，值是该单词出现的次数（在这个简单示例中是1）。
>    - **map 方法**：这个方法接收一个键（通常是文本数据的行号或偏移量）和一个值（文本数据的实际内容）。
>      - `tokenize(value)`：假设这是一个函数，用于将文本数据（`value`）分解为单词列表。
>      - `for (word <- tokenize(value))`：遍历每个单词。
>      - `emit(word, 1)`：为每个单词发出一个键值对。键是单词，值是1。
> 2. **Reducer 类**：
>    - **功能**：Reducer 的任务是聚合相同键的所有值（在此例中，键是单词）。它计算每个单词的总出现次数。
>    - **reduce 方法**：这个方法接收一个键（单词）和该键对应的所有值的集合（每个值都是1）。
>      - `for (value <- values)`：遍历每个值。
>      - `sum += value`：累加每个值（即1）以计算单词的总出现次数。
>      - `emit(key, sum)`：最后，为每个单词发出一个键值对。键是单词，值是该单词的总

```python
class Mapper {
	def map(key: Long, value: Text) = {
		val counts = new Map()
		for (word <- tokenize(value)) {
			counts(word) += 1
		}
		for ((k, v) <- counts) {
			emit(k, v)
		}
	}
}
```

This mapper uses a hash table (“counts”) to maintain the words and counts per line (i.e. in each call to the map function). After processing each line it emits the counts for this line.

> 
> 这段代码仍然表示 MapReduce 中的单词计数任务，但它在 Mapper 阶段引入了一种局部聚合或预聚合的技术。让我们深入了解其内容：
>
> Mapper 类：
>
> 1. **功能**：
>    - 这个 Mapper 的工作依然是处理输入的文本数据并为每个单词生成键值对。但不同之处在于，它不是为每个单词立即生成键值对，而是首先在本地累加单词的计数，然后才生成键值对。
> 2. **map 方法**：
>    - 接收两个参数：一个键（通常是文本数据的行号或偏移量）和一个值（文本数据的实际内容）。
>    - `val counts = new Map()`：初始化一个新的 Map（键值映射）来存储每个单词及其本地出现次数。
>    - `for (word <- tokenize(value))`：`tokenize` 函数将输入的文本值分解为单词列表。然后遍历这些单词。
>      - `counts(word) += 1`：对于每个单词，将其出现次数在 `counts` Map 中累加。
>    - `for ((k, v) <- counts)`：遍历 `counts` Map 中的每个条目（即每个单词及其计数）。
>      - `emit(k, v)`：为每个单词发出一个键值对。键是单词，值是该单词在当前处理的文本值中的出现次数。
>
> 总结：
>
> 这段代码的主要目的是减少 Mapper 输出的数量。通过在 Mapper 中进行局部聚合，可以减少需要传输到 Reducer 的数据量，从而提高 MapReduce 任务的效率。这种策略在处理大量数据时特别有用，因为它可以显著减少网络传输的开销。

```python
class Mapper {
	def map(key: Long, value: Text) = {
		val counts = new Map()
		for (word <- tokenize(value)) {
			counts(word) += 1
		}
	}
	
	def cleanup() + {
		for ((k,v) <- counts) {
			emit(k,v)
		}
	}
}
```

This mapper uses a hash table to maintain the words and counts across all lines in a single split.

By aggregating tuples across map tasks, this reduces disk and memory I/O. However, a possible drawback is **increasing the memory working set** (which is proportional to the number of distinct words in a map task)

> 这段代码还是描述了 MapReduce 中的单词计数任务，但它采用了一种不同的方法来处理 Mapper 的输出。具体地说，它引入了一个名为 `cleanup` 的方法来发出 Mapper 的输出，而不是在 `map` 方法中直接这样做。让我们详细分析这段代码：
>
> Mapper 类：
>
> 1. **map 方法**：
>
>    - **功能**：这个方法的工作仍然是处理输入的文本数据，并在本地为每个单词累计其出现次数。
>
>    - `val counts = new Map()`：初始化一个新的 Map 来存储每个单词及其本地出现次数。
>
>    - ```
>      for (word <- tokenize(value))
>      ```
>
>      ：
>
>      ```
>      tokenize
>      ```
>
>       函数将输入的文本值分解为单词列表。然后遍历这些单词。
>
>      - `counts(word) += 1`：对于每个单词，将其出现次数在 `counts` Map 中累加。
>
> 2. **cleanup 方法**：
>
>    - **功能**：此方法在 Mapper 的每个实例完成所有的 `map` 方法调用后被执行。它的目的是在所有输入都被处理后发出累积的键值对。
>
>     ```
>      for ((k,v) <- counts)
>      ```
>
>      ：遍历 
>
>      ```
>      counts
>      ```
>
>       Map 中的每个条目（即每个单词及其计数）。
>
>      - `emit(k,v)`：为每个单词发出一个键值对。键是单词，值是该单词在整个 Mapper 实例处理的所有文本值中的累计出现次数。
>
> 总结：
>
> 这段代码的主要变化是将键值对的输出从 `map` 方法移到了 `cleanup` 方法。这样做的优点是，对于 Mapper 处理的每一块输入数据，它只发出一次键值对，而不是为每个输入值发出多次。这种策略有助于减少 Mapper 到 Reducer 的数据传输，特别是当 Mapper 处理的输入数据块中有大量重复的单词时。

### Preserving State in Map / Reduce Tasks

![image-20231009233135957](https://images.wu.engineer/images/2023/10/09/image-20231009233135957.png)

## 2.5 Secondary Sort

- **Problem**: each reducer’s values arrive unsorted. But what if we want them to be sorted (e.g. sorted by temperature)?

- **Solution**: define a new ‘composite key’ as (K1, K2), where K1 is the original key (“Natural Key”) and K2 is the variable we want to use to sort
  - **Partitioner**: now needs to be customized, to partition by K1 only, not (K1, K2)

![image-20231010001527919](https://images.wu.engineer/images/2023/10/09/image-20231010001527919.png)

![image-20231010001534616](https://images.wu.engineer/images/2023/10/09/image-20231010001534616.png)

Compare by **yearMonth** first; if tie, compare by **temperature**

![image-20231010001547107](https://images.wu.engineer/images/2023/10/09/image-20231010001547107.png)

Partition by **yearMonth** only (not **temperature**)

> `Secondary Sort` 是 MapReduce 中的一个高级技术，它允许我们对 MapReduce 任务的输出不仅按键（key）进行排序，还可以按值（value）进行排序。在传统的 MapReduce 框架中，数据只能在 Reduce 阶段按键进行排序，但有时我们希望在同一个键下按值进行排序，这就是 Secondary Sort 的用武之地。
>
> ### 为什么使用 Secondary Sort？
>
> 考虑一个场景，我们想要按国家和每个国家的年份的数据进行排序。在这种情况下，"国家"是我们的主键，而"年份"是我们的次要键。我们不仅希望按国家进行排序，还希望在每个国家内部按年份进行排序。
>
> ### 如何实现 Secondary Sort？
>
> 1. **复合键**：为了实现 Secondary Sort，我们首先需要创建一个复合键，这个键包含我们的主键和次要键。在上述示例中，复合键将是（国家，年份）。
> 2. **自定义分区器**：我们需要一个自定义分区器来确保相同的主键总是被发送到同一个 Reducer。这是为了确保我们可以对所有相关的键值对进行排序。
> 3. **自定义分组比较器**：虽然我们使用复合键，但在进行分组时，我们只想根据主键进行分组。这确保了具有相同主键的所有键值对都发送到同一个 Reducer 的 `reduce` 方法。
> 4. **自定义排序比较器**：我们还需要定义如何对复合键进行排序，以便首先按主键排序，然后在主键相同的情况下按次要键排序。
>
> 通过上述步骤，当数据到达 Reducer 时，它将首先按主键进行分组，然后在每个主键组内部按次要键进行排序。这就实现了 Secondary Sort。
>
> 总的来说，Secondary Sort 是 MapReduce 中的一个技巧，用于对输出数据进行更细粒度的排序。虽然实现它需要一些额外的配置和定制，但它为处理和分析排序的数据提供了巨大的灵活性。

# 2b - Hadoop File System

## 2b.1 Distributed File System

- Don’t move data to workers, move workers to the data
  - Store data on the local disk of nodes in the cluster
  - Start up the workers on the node that has the data local
- A distributed system is the answer
  - GFS (Google File System) for Google’s MapReduce
  - HDFS (Hadoop Distributed File System) for Hadoop

> - 在大数据环境中，数据迁移成本很高，尤其是当我们谈论到TB或PB级别的数据。将数据从一个地方移动到另一个地方可能需要大量的时间和带宽。因此，与其移动大量的数据到计算节点上进行处理，不如将计算任务发送到存储数据的节点上，直接在数据所在地进行处理。这样，数据读取的延迟和网络带宽使用都大大降低。
>   - 数据应该分布存储在集群的每个节点上，使得每个节点既是数据的存储者，也是数据的处理者。
>   - 当需要对数据进行处理时，应该在存储该数据的节点上启动工作进程（workers）。这意味着计算会在数据所在的本地节点上执行，而不是在远程节点上。

### 2b.2 GFS/HDFS Assumptions (Pros of GFS/HDFS)

1. Commodity hardware instead of ‘exotic’ hardware

   这意味着它可以在相对便宜的机器上运行，从而降低成本。

2. High component failure rates

   由于HDFS是在普通的商用硬件上运行的，故障率可能会相对较高。HDFS的设计考虑到了这一点，并通过冗余和数据复制来确保数据的可靠性和可用性。

3. ‘Modest’ number of huge files

   HDFS是为存储少量的非常大的文件而设计的，而不是大量的小文件。

4. Files are write-once, mostly appended to

   一旦文件被写入HDFS，它们通常是只读的，并且主要是被追加内容。这种设计减少了数据的不一致性和复杂性。

5. Large streaming reads instead of random access

   HDFS是为大数据流读取而优化的，而不是随机访问。这意味着它特别适合顺序地读取大文件的应用，例如MapReduce。

   HDFS更关注持续的高吞吐量而不是低延迟。这与其用于大数据处理和分析的目的相符，这些任务通常需要读取和处理大量数据，而不是快速响应。

## 2b.3 Design Decisions

- Files stored as chunks
  - Fixed size (64MB for GFS, 128MB for HDFS)
- Reliability through replication
  - Each chunk replicated across 3+ chunkservers
- Single master to coordinate access, keep metadata
  - Simple centralized management

## 2b.4 HDFS Architecture

![image-20231010200054856](https://images.wu.engineer/images/2023/10/10/image-20231010200054856.png)

Q: How to perform replication when writing data?

A: Namenode decides which datanodes are to be used as replicas. The 1st datanode forwards data blocks to the 1st replica, which forwards them to the 2nd replica, and so on.

## 2b.5 Namenode Responsibilities

- Managing the file system namespace:
  - Holds file/dictionary structure, metadata, file-to-block mapping, access permissions, etc. Coordinating file operations
  - Directs clients to datanodes for reads and writes
  - No data is moved through the namenode
- Maintaining overall health:
  - Periodic communication with the datanode
  - Block re-replication and rebalancing
  - Garbage collection

Q: What if namenode’s data lost?

A: All files on the filesystem cannot be retrieved since there is no way to reconstruct them from the raw block data. Fortunately, Hadoop provides 2 ways of improving resilience, through backups and secondary namenodes (out of syllabus, but you can refer to Resources for details)

![image-20231010200417781](https://images.wu.engineer/images/2023/10/10/image-20231010200417781.png)

# 3 - Data Mining
## 3.1 Recap
#### Partition Step
![image.png](https://images.wu.engineer/images/2023/11/23/202311231339771.png)

- Note that key A went to reducer 1, and ket B went to reducer 2
- By default, the assignment of keys to reducers is determined by a **hash function** `h()`
	- e.g., key `k` goes to reducer `hash(k) % num_reducer`
- User can optionally implement a custom partition, e.g., to better spread out the load among reducers (if some keys have much more values than others)
#### Combiner
- The user must ensure that the combiner does not affect the correctness of the final output, whether the combiner runs 0, 1, or multiple times.
![image.png](https://images.wu.engineer/images/2023/11/23/202311231342316.png)

#### MapReduce Implementation
![image.png](https://images.wu.engineer/images/2023/11/23/202311231343993.png)

#### Preserving State in Mappers/Reducers
![image.png](https://images.wu.engineer/images/2023/11/23/202311231343686.png)

#### Combining HDFS and Hadoop
![image.png](https://images.wu.engineer/images/2023/11/23/202311231344984.png)

## 3.2 Secondary Sort
- **Problem**: each reducer's value arrive unsorted. But what if we want them to be sorted?
- **Solution**: define a new 'composite key' as (K1, K2), where K1 is the original key ("natural key"), and K2 is the variable we want to use to sort
	- Partitioner: now needs to be customised, to partition by K1 only, not (K1, K2)

> 在MapReduce框架中，数据是以键值对(key-value pairs)的形式进行处理的。在这个过程中，Map阶段生成的键值对会被分组(grouped)和排序(sorted)，然后传递给Reduce阶段。默认情况下，MapReduce只会按键（key）进行排序，这称为“自然排序”。
> 
> 如果我们需要以一种额外的方式对值进行排序，则这被称作为二次排序"secondary sort":
> - 定义一个新的“复合键”（composite key），格式为(K1, K2)，其中K1是原始键（也称为“自然键”），K2是我们希望用于排序的变量。在这种情况下，复合键将会影响如何对数据进行分区和排序：
> 	- **Partitioner**: 需要自定义分区器，使其仅按K1进行分区，而不是按复合键(K1, K2)分区。这样可以保证相同的K1会被发送到同一个reducer，但是在reducer内部，数据会根据K2的值进行排序。
> 这样，每个reducer接收的数据就会首先根据K1分组，然后在每个组内根据K2排序，实现了二次排序的目的

![image.png](https://images.wu.engineer/images/2023/11/23/202311231350907.png)

### Example
Assume we want to compute some statistics (median, 25% quantile) of the data **grouped by month**.
![image.png](https://images.wu.engineer/images/2023/11/23/202311231353189.png)

Our map function emits (month, temperature) tuples, so that tuples from the same month go to the same reducer.
However, the values (temperature) arrive at each reducer is **unsorted**.
![image.png](https://images.wu.engineer/images/2023/11/23/202311231353129.png)

Now we use (month, temperature) as **composite key**, but **without changing the partitioner**. 
The 4 tuples below have 4 different "values" of the composite key.
Recall that they will be partitioned by hashing the composite key values. So data with the same **primary key** may be sent to different reducers, which we don't want. 
![image.png](https://images.wu.engineer/images/2023/11/23/202311231355203.png)

Finally, **secondary sort** uses (month, temperature) as composite key, and uses a **custom partitioner**, to partition by month only.
Now we see that:
- Data for the same month goes to the same reducer
- At each reducer, data arrives sorted by temperature, since the MapReduce framework always **sort the data by the key** before giving it to each reducer
![image.png](https://images.wu.engineer/images/2023/11/23/202311231358050.png)

## 3.3 Relational Databases
- A relational database is comprised of tables
- Each table represents a relation = collection of tuples (rows)
- Each tuple consists of multiple fields

### Projection
```SQL
SELECT
	x,
	y
FROM
	Sales
```

![image.png](https://images.wu.engineer/images/2023/11/23/202311231400553.png)

### Projection in MapReduce
- **Map**: take in a tuple (with tuple ID as key), and emit new tuples with appropriate attributes
- No reducer needed (=> no need shuffle step)

### Selection
```SQL
SELECT * FROM Sales WHERE (price > 10)
```

![image.png](https://images.wu.engineer/images/2023/11/23/202311231402083.png)
### Selection in MapReduce
- **Map**: take in a tuple (with tuple ID as key), and emit only tuples that meet the predicate
- No reducer needed
![image.png](https://images.wu.engineer/images/2023/11/23/202311231403471.png)


### Group By
- Example: What is the average sale price per product?
- In SQL:
	- `SELECT product_id, AVG(price) FROM sales GROUP BY product_id`
- In MapReduce:
	- Map over tuples, emit <product_id, price>
	- Framework automatically groups these tuples by key
	- Compute average in reducer
	- Optimize with combiners

### Relational Joins (Inner Join)
![image.png](https://images.wu.engineer/images/2023/11/23/202311231406330.png)

### Broadcast (Map) Join
- Requires one of the table to fit in memory
	- All mappers store a copy of the small table (for efficiency: we convert it to a hash table, with keys as the keys we want to join by)
	- They iterate over the big table, and join the records with the small table
![image.png](https://images.wu.engineer/images/2023/11/23/202311231408758.png)

### Reduce-side (Common) Join
- Does not require a dataset to fit in memory, but slower than broadcast join
	- Different mappers operate on each table, and emit records, with keys as the variable to join by
- In reducer: we can use **secondary sort** to ensure that all keys from table X arrive before table Y
	- Then, hold the keys from table X in memory and cross them with records from table Y
![image.png](https://images.wu.engineer/images/2023/11/23/202311231409707.png)

### 3.3 Similarity Search
- We define "near neighbours" as points that are a "small distance" apart
- To measure the distance between objects x and y, we need a function `d(x, y)` which we call a "distance measure"
- **Similarity measures** are the opposite: lower distance = higher similarity, and vice versa

### Jaccard Similarity and Distance
- Jaccard Similarity
$$
S_{Jaccard}(A, B) = \frac {|A\cap B|} {|A \cup B|}
$$
![image.png](https://images.wu.engineer/images/2023/11/23/202311231418863.png)

- Jaccard Distance
$$
d_{Jaccard}(A,B) = 1 - s_{Jaccard}(A,B)
$$
### Essential Steps for Similar Docs
1. **Shingling**: Convert document to sets of short phrases ("shingles")
2. **Min-Hashing**: Convert these sets to short "signatures" of each document, while preserving similarity
	- A signature is just a block of data representing the content of a document in a compressed way
	- Document with the same signature are **candidate pairs** for finding near-duplicates
![image.png](https://images.wu.engineer/images/2023/11/23/202311231421220.png)
> **Shingling**（分词）：这一步将文档转换为一组短语（称为“shingles”或“k-grams”）。每个shingle通常是文档中连续的k个项（可以是字、词或字符）。例如，对于句子“The quick brown fox jumps over the lazy dog”，如果我们使用2-grams（bigrams）作为shingles，那么一个可能的shingle集合包括{"The quick", "quick brown", "brown fox", ...}。这一步的目的是创建文档的特征集，以便于比较。
> 
> **Min-Hashing**（最小哈希）：这一步的目的是将上一步得到的shingle集合转换为文档的“签名”（signature），这些签名在压缩数据的同时保留了文档间的相似性信息。签名是一个较短的数据块，它代表了文档内容的摘要。Min-hashing算法通过对每个文档的shingle集合使用哈希函数，将其转换为一个较短的哈希值序列（即签名），而且这一转换过程保留了原始shingle集合间的相似度结构。具有相同或相似签名的文档被认为是“候选对”（candidate pairs），这意味着它们很可能是近似重复的文档。
> 
> 这个过程是文档相似性检测的两个关键步骤：首先是将文档转换为一组能够代表其内容特征的shingles，然后是使用min-hashing算法将这些shingles集合转换为签名，这些签名可以用来有效地评估文档间的相似性。这个方法在处理大规模数据集时特别有效，因为它大大减少了需要比较的数据量。

### Shingles
- A **k-shingle** (or **k-gram**) for a document is a sequence of k tokens that appears in the doc
- *Examples*: `k=2, document D_1 = "the cat is glad"`, set of 2 shingles: $S(D_1)$ = {"the cat", "cat is", "is glad"}
- Each document $D_i$ can be thought of as a set of its k-shingles $C_i$
	- E.g. D = "the cat is" => C = {"the cat", "cat is"}

- Often represented as a matrix, where columns represent documents, and shingles represent rows
- We measure similarity between documents as **Jaccard Similarity**:
$$
sim(D_1, D_2) = \frac {|C_1 \cap C_2|} {|C1 \cup C_2|}
$$
![image.png](https://images.wu.engineer/images/2023/11/23/202311231428517.png)

### MinHash
- Suppose we have N=1 million documents
- Naively, we would have to compute **pairwise Jaccard similarities** for every pair of docs
- MinHash gives us a *fast approximation* to the result of using Jaccard similarities to compare all pairs of documents
![image.png](https://images.wu.engineer/images/2023/11/23/202311231430155.png)

- **Key Idea**: hash each column C to a small *signature* `h(C)`
	- `h(C)` is small enough that the signature fits in RAM
	- highly similar document usually have the same signature
- **Goal**: Find a hash function `h()` such that:
	- If `sim(C_1, C_2)` is high, then with high probability, `h(C_1) = h(C_2)`
	- Vice versa

Steps:
- Given a set of shingles, {(the cat), (cat is), (is glad)}
	1. We have a **hash function** h that maps each shingle to an integer:
	`h("the cat")=12, ...`
	2. Then compute the minimum of these: `min(12, 74, 48) = 12`
![image.png](https://images.wu.engineer/images/2023/11/23/202311231434831.png)
- Recall that we want to ensure that highly similar document have high probability to have the same MinHash signature
![image.png](https://images.wu.engineer/images/2023/11/23/202311231435813.png)

- Candidate pairs: the document with the same final signature are "candidate pairs". We can either directly use them as out final output, or compare them one by one to check if they are actually similar pairs.
- Extension to multiple hashes: in practice, we usually use multiple hash functions (e.g N=100), and generate N signatures for each document. "Candidate pairs" can be defined as those matching a "sufficient number" among these signature.

## 3.4 Clustering
- **Goal**: 
	- Clustering separates *unlabelled data* into groups of similar points
	- Clusters should have high intra-cluster similarity, and low inter-cluster similarity
![image.png](https://images.wu.engineer/images/2023/11/23/202311231439355.png)

### K-Means Algorithm
#### Initialisation
- Pick K random points as centers
![image.png](https://images.wu.engineer/images/2023/11/23/202311231440985.png)

#### Repeat
1. **Assignment**: assign each point to nearest cluster
2. **Update**: move each cluster center to the **average** of its assigned points
**Stop** if no assignments change

# 4 - NoSQL Overview
## 4.1 Introduction
- NoSQL mainly refers to a **non-relational database**, i.e. it stores data in a format other than relational tables
- "SQL" = Traditional Relational Database Management System (DBMS)
- NoSQL has come to stand for "Not Only SQL", i.e. using relational and non-relational databases alongside one another, each for the tasks they are most suited for
![image.png](https://images.wu.engineer/images/2023/11/23/202311240146688.png)

### Overview of NoSQL
1. Horizontally scalability
2. Replicate/distribute data over many servers
3. Simple call interface
4. Often weaker concurrency model than DBFS
5. Efficient use of distributed indexes and RAM
6. Flexible schemas

NoSQL数据库是一种设计来克服传统关系型数据库（RDBMS）的局限性的数据库管理系统。传统的关系型数据库依赖于严格定义的表和模式，而NoSQL数据库通常允许更加灵活的数据模型。这里简要概述NoSQL的特点及其相对于关系型数据库的优缺点：

1. **水平可扩展性**：NoSQL数据库可以通过增加更多的服务器来扩展数据库的存储和计算能力，而不是仅仅通过升级现有硬件的方式。
2. **复制/分布数据**：NoSQL数据库可以将数据复制到多个服务器，以实现高可用性和冗余。它们还可以将数据分布在多个服务器上，以提高查询的性能。
3. **简单的调用接口**：与SQL语言相比，NoSQL数据库通常提供更简单直接的方式来存储和检索数据。
4. **较弱的并发模型**：相比于RDBMS的事务和锁机制，NoSQL数据库可能提供较弱的一致性保证，通常采用最终一致性模型。
5. **分布式索引和RAM的高效使用**：NoSQL数据库能够高效地利用分布式索引和内存来快速响应查询。
6. **灵活的模式**：NoSQL数据库不需要预先定义的模式，可以存储结构化、半结构化或非结构化数据。

相对于传统关系型数据库，NoSQL数据库的**优点**包括：

- **可扩展性**：更容易扩展到多个服务器。
- **灵活性**：可以适应多变的数据模型和不断变化的数据类型。
- **高性能**：特别是在处理大量数据和高并发请求时。

NoSQL数据库的**缺点**可能包括：

- **一致性**：可能牺牲事务的严格一致性来获取性能和可扩展性。
- **复杂的数据关联**：对于需要复杂关联的数据，关系型数据库可能更加适合。
- **成熟度和工具**：相对于成熟的关系型数据库，NoSQL解决方案可能工具和支持较少。

NoSQL数据库牺牲严格一致性主要是为了提高系统的可扩展性和可用性。这是基于CAP定理的权衡，CAP定理指出，在一个分布式系统中，不可能同时保证以下三个要素：

1. **一致性（Consistency）**：每次读取都会返回最近一次写入的数据。
2. **可用性（Availability）**：每个请求都会收到一个（不管是成功还是失败的）响应。
3. **分区容忍性（Partition tolerance）**：系统可以在任何网络分区故障的情况下继续运行。

根据CAP定理，一个分布式系统只能同时满足这三个属性中的两个。NoSQL数据库通常选择可用性和分区容忍性，因为这对于大规模、分布式的系统是必要的。这意味着在某些情况下，为了保持系统的响应能力和持续服务，它们可能允许数据在短时间内是不一致的。这种设计选择是为了让系统在面对网络分区或其他故障时仍能继续操作，即使这意味着某些用户可能短暂地看到过时或不一致的数据。

这种不一致性通常是通过“最终一致性”来缓和的，这是一种保证，在没有新的更新的情况下，数据库最终会变得一致的方式。
## 4.2 Major Types of NoSQL systems
NoSQL数据库可以根据它们管理数据的方式分为几种主要类型：
1. **键值存储（Key-Value Stores）**：
    - 最简单的NoSQL数据库，以键值对的形式存储数据。
    - 例子：Redis, Amazon DynamoDB, Riak。
2. **文档存储（Document Stores）**：
    - 存储半结构化数据的文档，通常是JSON或XML格式。
    - 例子：MongoDB, CouchDB, Firestore。
3. **宽列存储（Wide-Column Stores）**：
    - 以列族为中心存储数据，允许存储大量数据。
    - 例子：Apache Cassandra, HBase, Google Bigtable。
4. **图形数据库（Graph Databases）**：
    - 使用图结构存储实体以及实体之间的关系，适合复杂的关系数据。
    - 例子：Neo4j, JanusGraph, Amazon Neptune。
### Key-Value Stores
#### Data Model
![image.png](https://images.wu.engineer/images/2023/11/23/202311240148996.png)
键值存储的一些特点包括：
1. **无模式**：键值存储通常不具备固定的模式或结构，数据可以以任何形式存储为值，如字符串、JSON、BLOB等。
2. **无关联**：它们不提供原生的方式来直接关联不同的键值对或模仿SQL中的表间连接。关系必须由应用逻辑来管理。
3. **单一的数据集合**：虽然某些键值存储系统可能允许你创建类似于“表”的不同命名空间或数据集合，但这些通常不提供连接功能。
4. **自定义索引**：在键值存储中，创建复杂索引需要应用层面的设计，比如通过维护一个特殊的键，它的值包含了需要被索引的数据项的键的列表。
**键值存储的优势**:
1. **性能**：键值存储提供非常快速的读写能力，因为它们通过键直接访问值，通常这些操作可以在O(1)时间内完成。
2. **可扩展性**：键值存储通常设计为易于水平扩展，能够处理更多的负载通过简单地增加更多的节点。
3. **简单性**：由于其简单的数据模型，键值存储通常更易于设置和维护。
4. **灵活性**：键值存储不需要预定义的模式，所以你可以随意存储不同结构的数据。

- Stores associations between keys and values
- Keys are usually primitives and can be queried
- Values can be primitive or complex; usually cannot be queried
#### Operations
- Very simple API
	- `get` - fetch value associated with key
	- `put` - set value associated with key
- Optional operations
	- `multi-get`
	- `multi-put`
	- `range queries`
- Suitable for:
	- Small continuous read and writes
	- Storing 'basic' information, or no clear schema
	- When complex queries are not required / rarely required
#### Implementation
- Non-persistent:
	- Just a big in-memory hash table
- Persistent:
	- Data is stored persistently to disk
### Document Stores
文档存储NoSQL数据库是一种旨在存储、检索和管理面向文档的信息的数据库系统。这里的“文档”并非指文字处理文档，而是指一种可以包含复杂数据结构的数据记录。文档通常以JSON、BSON（二进制JSON）、XML等格式存储，并且每个文档都可以有一个独特的结构。

以下是文档存储NoSQL数据库的一些关键特点：
1. **灵活的数据模型**：文档可以包含嵌套的数据结构，如数组和子文档。由于没有固定的模式，文档的结构可以动态更改。
2. **自描述性**：文档存储通常是自描述的，意味着数据结构描述包含在文档本身中，这使得数据的解析和理解变得直观。
3. **查询能力**：大多数文档数据库提供了强大的查询语言，允许用户执行复杂的搜索、聚合和过滤操作。
4. **索引**：为了提高查询性能，文档数据库支持在一个或多个文档的属性上建立索引。
5. **扩展性**：文档数据库也设计为易于水平扩展，允许通过增加更多的服务器来增加数据库的容量和吞吐量。
6. **API接口**：文档数据库通常提供丰富的API用于交互，这些API可以是RESTful的，也可以是数据库专有的查询语言。

文档数据库的一个主要优势在于其灵活性。它们允许开发者在不需要预先定义表结构的情况下存储和查询数据，这对于快速开发和迭代、以及处理非结构化或半结构化数据非常有利。

然而，文档数据库也有其局限性，如它们可能不支持像传统SQL数据库那样复杂的事务管理，而且当涉及到多个文档或集合时，维护数据一致性可能会更加复杂。

代表性的文档存储NoSQL数据库包括：
- **MongoDB**：存储BSON文档，并提供丰富的查询语言和索引功能。
- **CouchDB**：使用JSON进行存储，并提供MapReduce作为查询和索引机制。
- **Firestore**：Google提供的文档数据库，以实时同步和服务器端逻辑著称。
#### Data Model
![image.png](https://images.wu.engineer/images/2023/11/23/202311240157401.png)
- A database can have multiple **collections**
- Collections have multiple **documents**
- A document is a JSON-like object: it has **fields and values**
	- Different documents can have different fields
	- Can be nested: i.e. JSON objects as values
![image.png](https://images.wu.engineer/images/2023/11/23/202311240158758.png)
#### Querying
- Unlike basic key value stores, document stores allow some querying based on the content of a document
- CRUD = Create, Read, Update, Delete
##### Create
![image.png](https://images.wu.engineer/images/2023/11/23/202311240159859.png)
##### Read
![image.png](https://images.wu.engineer/images/2023/11/23/202311240159879.png)
##### Update
![image.png](https://images.wu.engineer/images/2023/11/23/202311240159380.png)
##### Delete
![image.png](https://images.wu.engineer/images/2023/11/23/202311240159910.png)
### Wide Column Stores
宽列存储（Wide-Column Store）是NoSQL数据库的一种类型，它兼具了传统关系数据库和非关系型键值存储的一些特性。这种数据库类型特别适用于处理大量数据以及需要高度可扩展性和灵活性的应用。与传统的关系型数据库不同，宽列存储在逻辑上通过列族而非行来组织数据。

以下是宽列存储的一些核心特点：
1. **列族（Column Families）**：
    - 数据被存储在列族中，每个列族是一个容器，存储着相关的列。
    - 列族内的列可以在每一行中不同，允许每行有不同的列数和类型，这带来了极大的灵活性。
2. **行键（Row Keys）**：
    - 每一行由一个唯一的行键（Row Key）标识，可以用来快速访问和检索数据。
3. **动态列**：
    - 每行可以有数千甚至数百万列，列可以在运行时动态地增加到任何行中，不需要预先定义模式。
4. **可扩展性**：
    - 宽列存储设计用于水平扩展，可以通过增加更多的服务器节点来提高容量和吞吐量。
5. **优化读/写性能**：
    - 通过将相关数据存储在相同的列族中，宽列存储可以优化数据的读取和写入性能。
6. **分布式架构**：
    - 它们通常自带分布式架构，能够处理大规模数据分布在多个物理位置。

宽列存储的一些典型应用场景包括：
- **大数据分析**：由于其能够处理大量的动态列，它适合于数据挖掘和分析。
- **时间序列数据**：例如，股票行情、事件日志和监控数据。
- **推荐系统**：可以存储和处理用户与内容的多维关系。

一些著名的宽列存储NoSQL数据库包括：
- **Apache Cassandra**：提供高可用性和可扩展性，适用于需要容错的应用。
- **Google Bigtable**：是Google的分布式存储系统，用于管理大型数据集。
- **HBase**：建立在Hadoop文件系统之上，用于提供随机实时读/写访问大数据。
#### Data Model
- Rows describe entities
- Related groups of columns are grouped as **column families**
- **Sparsity**: if a column is not used for a row, it doesn't use space
![image.png](https://images.wu.engineer/images/2023/11/23/202311240201955.png)
### Graph Databases
图形数据库（Graph Databases）是一种NoSQL数据库，它们使用图论的概念存储、查询和操作数据。在图形数据库中，数据结构被视为点（Nodes）、边（Edges）和属性（Properties）。它们特别适用于表示和查询数据之间复杂的关联和网络。

**核心概念**：
1. **节点（Nodes）**：
    - 节点代表实体，如人、业务、账户、计算机等。
    - 每个节点可以有一个或多个标签（Labels）来表示不同的类别或类型。
    - 节点可以包含多个属性（键值对），用以存储关于实体的信息。
2. **边（Edges）**：
    - 边代表节点之间的关系。
    - 每条边都有一个类型，表明连接的节点之间的关系性质，如“朋友”、“属于”或“访问”。
    - 边也可以有属性，提供有关关系的更多信息，如权重、成本、距离等。
3. **属性（Properties）**：
    - 节点和边都可以有属性，这些属性以键值对的形式存在。
    - 属性为图数据添加了丰富的语义。
4. **索引（Indexes）**：
    - 图形数据库通常支持通过索引来加速对节点和边的查询。

**图形数据库的特点**：
1. **关系优先**：图形数据库将关系作为一等公民，这与其他数据库系统不同，在那里关系通常是通过外键或特殊的索引来表示的。
2. **性能**：对于深度连接查询和复杂的关系网络，图形数据库可以提供卓越的性能。
3. **灵活性**：图结构的自然灵活性使得添加新的关系和节点不需要更改现有的数据模式。
4. **直观性**：图形数据库的结构使得数据模型和现实世界的网络直观对应，方便理解和查询。

**流行的图形数据库**：

- **Neo4j**：最流行的图形数据库之一，提供了一个富有表达力的图查询语言Cypher。
- **JanusGraph**：开源的，可扩展的图形数据库，支持各种后端存储。
- **Amazon Neptune**：AWS提供的图形数据库服务，支持开放图形查询语言（Gremlin）和RDF查询语言（SPARQL）。
![image.png](https://images.wu.engineer/images/2023/11/23/202311240202326.png)
### Vector Databases
矢量数据库（Vector Databases）是专门设计来存储和查询矢量空间数据的数据库系统。在这个上下文中，“矢量”通常指的是多维的数值数组，它们代表了数据点在特定的特征空间中的位置。这种类型的数据库在处理大规模机器学习和人工智能任务中尤为重要，尤其是在执行相似性搜索时。

**核心概念**：
1. **特征向量（Feature Vectors）**：
    - 在机器学习和搜索领域，数据项经常被转换成特征向量，这些特征向量表示了数据项的特性或属性。
2. **相似性搜索（Similarity Search）**：
    - 矢量数据库的主要功能之一是快速找到与给定查询向量相似的向量。相似性度量通常使用余弦相似度、欧几里得距离等方法。
3. **索引和优化**：
    - 为了高效地进行相似性搜索，矢量数据库使用多种索引和优化技术，如树结构、哈希技术或分区策略。

**矢量数据库的特点**：
1. **高效的搜索性能**：
    - 矢量数据库能够在高维空间中快速执行k最近邻（k-NN）搜索，这对于实时推荐系统、图像或视频检索等是至关重要的。
2. **大规模数据处理**：
    - 它们可以处理数以亿计的向量，并且在这样的规模上仍能保持查询的响应时间。
3. **机器学习集成**：
    - 矢量数据库经常与机器学习模型和流程紧密集成，以便直接利用模型生成的特征向量。

- Store **vectors**
	- Usually dense, numerical, and high-dimensional
- Allow fast **similarity search**, i.e., given a query, retrieve similar neighbours from the database
- DB features: scalability, real-time updates, replication
## 4.3 Key Concepts
- Strong consistency
	- any reads immediately after an update must give the same result on all observers
	- all reader read new value
- Eventual consistency
	- If the system is functioning and we wait long enough, eventually all reads will return the last written value
	- readers may read old value

- ACID
	- Relational DBMS provide stronger (ACID) guarantees
	- **ACID**是传统关系型数据库的设计理念，它强调的是数据操作的可靠性和一致性：
		1. **原子性（Atomicity）**：事务中的所有操作都是一个不可分割的工作单位，要么全部完成，要么全部不做。
		2. **一致性（Consistency）**：事务执行结果必须使数据库从一个一致性状态转变到另一个一致性状态。
		3. **隔离性（Isolation）**：并发执行的事务之间不会互相影响。
		4. **持久性（Durability）**：一旦事务提交，其所做的修改将永久保存在数据库中。
- BASE
	- In many NoSQL system provide weaker "BASE" approach
	- **BASE**则是许多NoSQL数据库系统遵循的理念，它更强调系统的可用性和容错性：
		1. **基本可用（Basically Available）**：系统保证可用性，但可能因为响应时间的延迟或系统功能的减少而不是完全可用。
		2. **软状态（Soft state）**：系统的状态可能会随时间而改变，即使没有输入，系统状态仍然有可能变化（例如，由于数据复制而导致的状态变化）。
		3. **最终一致性（Eventual consistency）**：系统保证，如果没有新的更新操作，数据最终将达到一致状态。

- Duplication (Denormalisation)
	- 去规范化（Denormalization）是数据库优化的一个过程，特别是在关系型数据库的上下文中。去规范化涉及减少数据库的规范化级别，通常通过合并表格、添加冗余数据或组合字段来实现。其主要目的是提高数据库的查询性能，尤其是在大数据量和复杂查询的情况下。
	- 在典型的关系型数据库中，规范化是一个将数据组织到多个相关表中以减少冗余和依赖性的过程。规范化有很多级别（正规形式），每个级别都旨在减少数据冗余和提高数据完整性。然而，高度规范化可能导致性能问题，因为复杂的查询可能需要多个表之间的连接操作，这在大型数据库中可能会非常耗时。
	- 去规范化的策略包括：
		1. **添加冗余列**：在一个表中包含来自另一个表的数据，以避免连接操作。
		2. **合并表**：将多个相关的表合并为一个表，以减少查询中的连接数量。
		3. **预计算聚合**：存储计算结果（如总和、平均值等）而不是在每次查询时都重新计算。
		4. **创建冗余索引**：创建额外的索引来加速查询，即使这些索引会占用更多的存储空间。
	- 去规范化的缺点是可能导致数据更新、插入和删除操作的复杂性增加，因为需要维护额外的冗余数据的一致性。此外，它也增加了存储需求，因为相同的数据会在多个地方存储副本。
	- 在设计数据库和数据存储解决方案时，去规范化是一种常见的权衡策略，它需要在查询性能和数据冗余之间找到平衡。
# 5 - NoSQL and Basic of Distributed Databases
## 5.1 Basic Concept of Distributed Databases
- 分布式数据库是一种可以在网络的不同节点上分布存储数据的数据库系统。在分布式数据库系统中，数据可能被分散在一个网络中的多个物理位置上，而这个网络可以是在同一个物理位置的局部网络，也可以是跨越广泛地理区域的远程网络节点。

- 分布式数据库的主要目的是为了满足以下需求：
1. 可扩展性：系统应当能够添加更多的机器来处理额外的数据。
2. 可用性：系统即便在部分故障的情况下也能保持工作。
3. 耐用性：系统能够保证数据不会因故障而丢失。
4. 性能：通过数据的分布式存储和并行处理，提高数据库操作的效率

- Why distributed databases?
	- **Scalability**: allow database sizes to scale simply by adding more nodes (servers)
	- **Availability / Fault Tolerance**: if one node fails, others can still serve requests
	- **Latency**: generally, each request is served by the closet replica (node), reducing latency, particularly when the database is distributed over a wide geographical area
### Data Transparency
- Users should not be required to know how the data is physically distributed, partitioned, or replicated
- A query that works on a single node database should still work on a distributed database
数据透明性是指用户在使用数据库时不需要了解背后的数据如何存储、分区、或复制的细节。这意味着，从用户的视角来看，他们是在与一个单一的、统一的数据库进行交互，尽管实际上数据可能分布在多个不同的节点上。

换句话说，对于用户来说，无论是在单个数据库节点上执行查询，还是在分布式数据库系统上执行，查询的编写方式和结果都应该是一致的。用户的查询应当独立于数据的物理布局，数据库系统的内部机制负责处理数据的定位、访问和管理，对用户完全透明。

这样做的好处是简化了数据库的使用，用户可以专注于查询和数据操作，而不需要担心背后的复杂性。同时，这也提供了数据库管理的灵活性，因为数据库管理员可以在不影响用户的情况下，优化数据的存储和处理。
### Assumption of Distributed Databases
- All nodes in a distributed database are well-behaved (i.e., they follow the protocol we designed for them; not "adversarial" or trying to corrupt the database)
### Distributed Database Architectures
![image.png](https://images.wu.engineer/images/2023/11/24/202311241755193.png)
## 5.2 Data Partitioning
### Table Partitioning
- Put different tables (or collections) on different machines
![image.png](https://images.wu.engineer/images/2023/11/24/202311242028786.png)
- Problem:
	- scalability - each table cannot be split across multiple machines
表分区（Table Partitioning）是数据库管理系统中用于管理大型表数据的一种技术。通过这种技术，一个大表被分解为多个更小、更易于管理的逻辑分区，但在逻辑上仍然作为单个表对外呈现。每个分区可以存储在不同的物理位置，且可以单独优化和维护。表分区通常用于提高查询性能、优化数据加载、提高数据维护效率以及改善备份恢复操作的速度。
表分区的主要优点包括：
- **性能提升**：查询可以仅在相关的分区上执行，减少了数据扫描的范围。
- **维护简化**：对于数据的维护操作（如备份、恢复、清理旧数据）可以在分区级别进行，而不必对整个表操作。
- **数据分布优化**：可以将不同的分区存放在不同的存储介质上，根据访问频率和性能要求进行优化。
### Horizontal Partitioning
- Different tuples are stored in different nodes
- Also called 'sharding'
- **Partition Key** (or shard key) is the variable used to decide which node each tuple will be stored on: tuples with the same shard key will be on the same node.
	- How to choose partition key?
		- If we  often need to filter tuples based on a column, or "group by" a column, then that column is a suitable partition key
水平分区（Horizontal Partitioning）也称作分片（Sharding），以及如何选择合适的分区键（Partition Key）或分片键（Shard Key）。
1. **不同的元组存储在不同的节点**： 这意味着在一个分布式数据库系统中，表中的每一行（或称作元组）根据某种规则，被分散存储在不同的数据库节点上。这些节点可以是同一个数据中心内的不同服务器，也可以是分布在不同地理位置的服务器。
2. **Partition Key 分区键**（或shard key分片键）： 分区键是用来决定每个元组存储位置的变量。根据分区键的值，数据库管理系统将元组分配到不同的节点上。拥有相同分区键值的元组会被存储在相同的节点上。
3. **如何选择分区键**： 选择分区键是一个重要的决策，因为它会直接影响查询的效率和系统的扩展性。理想的分区键应该满足以下条件：
    - **查询过滤**：如果某个列经常被用作查询条件（WHERE子句），那么这个列可能是一个好的分区键。
    - **分组统计**：如果经常需要按某个列进行分组（GROUP BY子句）进行聚合运算，那么这个列也可能是一个好的分区键。
    - **负载均衡**：分区键应该能够确保数据和负载在各个节点间均匀分布，避免某个节点数据量过大或查询负载过高。
![image.png](https://images.wu.engineer/images/2023/11/24/202311242043316.png)

- 分区键的选择:
	- 假设在电子商务公司中，有一个数据库存储着用户信息,如果我们使用 city_id 为分区键:
		- 如果我们经常根据城市检索数据,那么这个分区键是可以的.
		- 如果城市的数量很少: 我们称之为 low cardinality 低基数

#### Range Partition
- Range Partition: split key based on range of values
	- Beneficial if we need range-based queries. In the above example, if the user queries for user_id < 50, all the data in partition 2 can be ignored ('partition pruning'); this saves a lot of work
	- But: range partitioning can lead to imbalanced shards, e.g., if many rows have user_id = 0
	- Splitting the range is automatically by a balancer (it tries to keep the shards balanced)
1. **范围分区**： 范围分区是通过确定键值的范围来实现的。数据库系统根据预设的键值范围，把数据分散到不同的分区。例如，user_id 在1到100的用户记录可能存储在分区1，而user_id 在101到200的记录存储在分区2。
2. **范围查询的效益**： 如果经常需要执行基于范围的查询，例如查询 user_id 小于50的所有用户，那么范围分区非常有用。在这种情况下，查询时可以跳过不包含相关数据的分区（如上例中的分区2），这种方法称为“分区裁剪”（Partition Pruning），它可以显著节省查询处理的工作量。
3. **可能导致分区不平衡**： 范围分区可能会导致数据分布不均衡。例如，如果大量行的 user_id 都是0，那么这些行都会被存储在同一个分区中，这会导致该分区数据过多，而其他分区数据不足。
4. **自动的范围划分**： 通常，分布式数据库系统会有一个“平衡器”（Balancer）功能，自动调整分区范围，试图保持各个分区的数据量平衡。这意味着系统会监控数据的分布情况，并在必要时重新划分分区范围，以保持分区之间的均衡。
![image.png](https://images.wu.engineer/images/2023/11/24/202311242122129.png)
#### Hash Partition
- **Hash Partition**: hash partition key, then divide that into partitions based on ranges
	- Hash function automatically spreads out partition key values roughly evenly
- 哈希分区是一种使用哈希函数来决定数据存储位置的方法。在这种策略中，系统会根据分区键的哈希值将数据项分配到不同的节点或分区上。哈希分区的关键点在于，它使用一个哈希函数将键值域映射到一个固定范围的分区标识符上。它通常能够保证数据被均匀分布在所有的分区上，避免了范围分区可能出现的数据倾斜问题。
### Consistent Hashing
- Think of the output of the hash function as lying on a circle:
![image.png](https://images.wu.engineer/images/2023/11/24/202311242124109.png)
- How to partition: each node has a 'marker' (rectangles)
	- Each tuple is placed on the circle, and assigned to the node that comes clockwise after it
- To delete a node, we simply re-assign all its tuples to the node clockwise after this node
- Similarly, to *add a node*, we add a new marker, and re-assigning all tuples which now belong to the new node
- **Simple replication strategy**: replicate a tuple in the next few additional nodes clockwise after the primary node used to store it
- Multiple markers: we can also have multiple markers per node. For each tuple, we still assign it to the marker nearest to it in the clockwise direction.
	- Benefit: when we remove a node, its tuples will not all be reassigned to the same node. So, this can balance load better
1. **环形哈希空间**：
    - 将哈希函数的输出想象为分布在一个圆环上，这个圆环代表了一个连续的哈希值空间。
2. **如何进行分区**：
    - 每个节点在这个圆环上有一个“标记”（通常可以想象为一个矩形或点），代表其在哈希空间上的位置。
    - 每个元组（数据项）根据其哈希值被放置到圆环上的某个位置，然后分配给顺时针方向上的第一个节点标记。
3. **删除节点**：
    - 当需要删除一个节点时，圆环上的这个节点标记被移除，原本分配给这个节点的所有元组会被重新分配给顺时针方向上的下一个节点。
4. **添加节点**：
    - 相似地，添加一个新节点时，在圆环上为其增加一个新的标记，并将现在应该属于这个新节点的元组重新分配给它。
5. **简单复制策略**：
    - 可以通过在顺时针方向上的几个额外节点中复制元组来实现元组的简单复制，以增加数据的可用性和耐久性。
6. **多重标记**：
    - 每个节点可以在圆环上拥有多个标记。对于每个元组，依然是分配给顺时针方向上最近的标记。
    - 这样做的好处是，当删除一个节点时，其元组不会全部重新分配给同一个节点，这有助于更好地平衡负载。
## 5.3 Query Processing in NoSQL
### Architecture of MongoDB
![image.png](https://images.wu.engineer/images/2023/11/25/202311251512094.png)

- MongoDB是一种文档型数据库
- MongoDB的分布式架构主要由三个核心组件构成：路由器（Routers），配置服务器（Config Servers）和副本集（Replica Sets）。这种架构支持MongoDB的分片功能，允许数据库跨多个服务器进行横向扩展。下面是每个组件的具体作用：
#### 路由器（Routers）
- 路由器在MongoDB中通常指的是`mongos`实例。`mongos`的作用是作为前端服务，接受客户端的数据库操作请求，并将这些请求路由到正确的数据分片上。
- 客户端不直接与存储数据的节点通信，而是通过`mongos`来进行。当一个查询被执行时，`mongos`会确定需要访问哪些分片，并将查询转发到这些分片上。
- 在一个拥有多个分片的大型系统中，可能会有多个`mongos`实例来分散客户端请求的负载。
#### 配置服务器（Config Servers）
- 配置服务器存储了整个MongoDB集群的元数据和配置信息。这包括分片的信息、路由策略、副本集的配置等。
- 在集群中，通常有三个配置服务器实例来保证高可用性和数据一致性。
- `mongos`查询这些配置信息来了解数据的分布情况，并据此将客户端请求路由到正确的分片。
#### 副本集（Replica Sets）
- 副本集是MongoDB提供数据冗余和高可用性的方式。一个副本集包含了多个数据节点，其中一个是主节点，其他是从节点。
- 主节点处理所有的写操作，而从节点则复制主节点的数据变更。这样可以在主节点出现故障时自动切换到从节点，继续提供服务，无需数据丢失的风险。
- 副本集也可以用于读取分离，即读操作可以在从节点上进行，分担主节点的读取压力。
### Example of Read or Write Query
- For example, a query `find({'class': 'cs5425'})` is pushed from the app
	1. Query is issued to a **router** (`mongos`) instance
	2. With help of **config server**, `mongos` determines which shard (**replica set**) to query
	3. Query is sent to the relevant shards (partition pruning)
		- 分区裁剪（Partition Pruning）是数据库查询优化器用来提高查询效率的一种技术。当查询操作针对一个分区表执行时，查询优化器会分析查询条件，以决定是否有些分区可以被排除在查询之外，因为它们不包含符合条件的数据。这样，数据库在执行查询时就不会扫描这些不相关的分区，从而节省了时间和计算资源。
		- Example: when reading a specific value of the shard key, the config server can determine that the query only needs to go to one shard (the one that contains the value of the shard key); writes are similar
		- But if the query is based on a key other than the shard key, which is relevant to all shards, and the query will go to all shards
	4. Shards run query on their data, and send results `{'name': 'bob', 'class': 'cs5425'` back to `mongos`
	5. `mongos` merge the query results and returns the merged results to the application
### Replication in MongoDB
- Common configuration: 1 primary, 2 secondaries
![image.png](https://images.wu.engineer/images/2023/11/25/202311251532107.png)
- Write operation:
	- The *primary* receives all write operations
	- Records writes onto its 'operation log'
	- Secondaries will then replicate this 'operation log', and apply it to their local copies of the data (which ensuring data is synced), then acknowledge the operation to the primary
- Read operation:
	- The user can configure the "read preference", which decides whether we can read from secondaries (this is the default), or the primary
	- Allowing reading from secondaries can **decrease latency** and **distribute load** (improving throughput), but allows for reading *stale data* (only for eventual consistency)
- Elections:
	- If the primary node *fails*, the nodes "conduct and election", which is a protocol to choose one of the secondaries to be promoted to primary
## 5.4 Conclusion: Reasons for Scalability & Performance of NoSQL
- **Horizontal partitioning**: as we get more and more data, we can simply partition it into more and more shards (even individual tables becomes very large)
	- Horizontal partitioning improves speed due to parallelisation
- **Duplication**: Unlike relational DBs where queries may require looking up multiple tables (joins), using duplication in NoSQL allows queries to go to only one collection
- Relaxed consistency guarantees: prioritise availability over consistency - can return slightly stale (wrong, un-updated) data

# 6 - Spark I: Basics
## 6.1 Introduction and Basics
### Motivation: Hadoop vs Spark
![image.png](https://images.wu.engineer/images/2023/11/25/202311251620074.png)
- Issues with Hadoop MapReduce
	- **Network and disk I/O costs**: intermediate data has to be written to local disks and shuffled across machines, which is *slow*
	- **Not suitable for iterative processing**(i.e., modifying small amounts of data repeatedly): such as interactive workflows, as each individual step has to be modelled as a MapReduce job.
- Spark Stores most of its intermediate results in memory, making it much faster, especially for iterative processing.
	- When memory is insufficient, Spark **spills to disk** which requires disk I/O
Hadoop在MapReduce的过程中，中间数据需要被写入到磁盘，并在机器间进行数据洗牌，这个过程是缓慢的。因为每次任务运行完之后，输出都需要写到磁盘，再被下一个任务读取，这造成了高磁盘开销。
同时，MapReduce不适合迭代处理，迭代处理指的是多次地对数据集进行操作，每次只修改一小部分数据。在Hadoop中，迭代处理的每一步都会被创建为一个独立的MapReduce任务，这使得效率变得低下。

**Spark**设计了一种不同的数据处理模型，它能够将大部分中间结果存储在内存中，这使得数据处理速度大大提升，尤其是对于需要多次迭代的计算任务，例如图算法或者机器学习算法。因为这些任务需要多次读取和处理数据，使用Spark可以显著减少读写磁盘的次数，从而提高速度。
当内存不足以存储所有中间结果时，Spark会将数据“溢出”到磁盘，这仍然需要磁盘I/O，但这样的设计意味着只有在必要时才会访问磁盘，而不是像Hadoop那样的频繁磁盘读写。
### Spark Components and API Stack
![image.png](https://images.wu.engineer/images/2023/11/25/202311251620090.png)
### Spark Architecture
![image.png](https://images.wu.engineer/images/2023/11/25/202311251621778.png)
- **Driver Process** responds to user input, manages the Spark application etc., and distributes work to **Executers**, which run the code assigned to them and send the results back to the driver
- **Cluster Manager** (can be Spark's standalone cluster manager, YARN, Mesos or Kubernetes) allocates resources when the application requests it
- In **local mode**, all these processes run on the same machine
- **驱动进程(Driver Process)**:
	- 驱动进程是Spark应用程序的主控制节点。它负责响应用户的输入，管理Spark应用程序的生命周期（如启动、停止），并且负责将工作分配给执行器。
	- 驱动进程执行用户编写的主程序，并且创建出一个`SparkContext`对象。这个`SparkContext`会与集群管理器(Cluster Manager)通信，申请资源并在资源被分配后，将代码任务分发给集群中的执行器（Executors）。
- **执行器(Executer)**:
	- 执行器是在集群中的工作节点上运行的进程，它们负责执行由驱动进程(Driver Process)分配给它们的代码，并返回计算结果。
	- 每个执行器负责处理分配给其的数据，并执行任务。执行器还负责存储它们计算的结果数据，这些数据可能是RDDs（弹性分布式数据集）的一部分，或者是广播变量和累加器。
- **集群管理器（Cluster Manager）**：
	- 集群管理器负责在Spark应用程序请求时分配计算资源。。
	- 集群管理器的主要角色是在计算资源（如CPU和内存）和集群中可用的物理机器之间进行资源调度。
- **本地模式（Local Mode）**：
	- 当Spark在本地模式下运行时，上述所有的进程（驱动进程、执行器、甚至是模拟的“集群管理器”）都会在同一台机器上运行。
### Evolution of Spark APIs
![image.png](https://images.wu.engineer/images/2023/11/25/202311251631816.png)
- RDD (Resilient Distributed Datasets) 弹性分布式数据集:
	- A collection of JVM objects
	- Functional operators (map, filter, etc.)
- DataFrame
	- A collection of Row objects
	- Expression-based operations
	- Logical plans and optimizer
- DataSet
	- Internally rows, externally JVM objects
	- Almost the "Best of both side": type safe + fast
## 6.2 Working with RDDs
RDD（Resilient Distributed Dataset）是Spark中的一个基本概念，是一个不可变的、分布式的数据对象集合，能够并行操作。RDD可以跨集群的多个节点分布存储数据，提供了一种高度的容错性、并行性和灵活性。
RDD的主要特点包括：
1. **不可变性**：一旦创建，RDD的数据就不可以被改变。这有助于容错，因为系统可以根据原始数据源重新构建RDD。
2. **弹性**：RDD能够在节点失败时重新构建丢失的数据分区，因为RDD的操作都是基于转换的，这些转换是可以记录的，并且是确定性的。这意味着如果某个节点的数据丢失，Spark可以使用原始数据和转换操作日志来重新计算丢失的数据分区。
3. **分布式**：RDD的数据自动被分散到集群中的多个节点上，可以在这些节点上并行处理。
4. **基于转换的操作**：RDD的操作是通过转换（如`map`、`filter`、`reduce`等）来实现的，每个转换操作都会生成一个新的RDD。转换是懒执行的，也就是说，只有在需要结果的时候才会执行。
5. **容错性**：RDD通过记录转换的 lineage（血统信息）来提供容错能力。如果由于某种原因某个分区的数据丢失，Spark可以通过这个 lineage 来重新计算丢失的分区数据。
6. **内存和磁盘存储**：RDD可以存储在内存中，也可以存储在磁盘上，或者两者的组合。根据RDD的存储和持久化策略，可以优化性能。
- Resilient Distributed Datasets (RDD)
	- **Resilient**: Achieve fault tolerance through *lineages*
	- **Distributed Datasets**: Represent a collection of objects that is *distributed over machines*
### RDD: Distributed Data
```Python
# Create an RDD of names, distributed over 3 partitions
dataRDD = sc.parallelize(["Alice", "Bob", "Carol", "Daniel"], 3)
```
- `sc.parallelize()` partition data into specific parts (here is 3)
- RDDs are **immutable**, i.e., they cannot be changed once created
- This is an RDD with 4 strings. In actual hardware, it will be partitioned into the 3 workers.
![image.png](https://images.wu.engineer/images/2023/11/25/202311251636047.png)
### Transformations
转换（Transformation）是对数据集进行操作的函数，它接收当前的RDD，应用一个计算函数，并返回一个新的RDD。转换是**惰性**执行的，也就是说，它们不会立即计算结果。只有在行动（Action）操作请求时，例如当需要将数据保存到文件或者将数据集聚合计算结果返回给驱动程序时，转换才会被触发执行。
- **Transformations** are a way of transforming RDDs into RDDs
```Python
dataRDD = sc.parallelize(["Alice", "Bob", "Carol", "Daniel"], 3)
# Create a new RDD which stores the length of names
nameLen = dataRDD.map(lambda s: len(s))
```
- This represents the transformation that maps each string to its length, and creating a new RDD
- However, the transformations are **lazy**. This means the transformation will **not be executed** until an **action is called** on it.
	- For example, save this RDD to a file will trigger the transformation to execute
	- The advantages of being lazy is that Spark can optimise the query plan to improve speed
- Example of transformations: `map`, `order`, `groupBy`, `filter`, `join`, `select`
### Actions
- **Actions** trigger Spark to compute a result from a series of transformations
```Python
dataRDD = sc.parallelize(["Alice", "Bob", "Carol", "Daniel"], 3)
nameLen = dataRDD.map(lambda s: len(s))
# Take action
nameLen.collect()
```
```Bash
[5, 3, 5, 6]
```
- `collect()` here is an action
	- It is the action that asks Spark to retrieve all elements of the RDD to the driver node
	- Driver Node是指运行Driver Process，用户应用程序的*主节点*
- Examples of actions: `show`, `count`, `save`, `collect`
### Distributed Processing
- As we previously said, RDDs are actually distributed across machines.
- Thus, the transformations and actions are executed in parallel in workers. The results are sent to the driver node in the final step.
![image.png](https://images.wu.engineer/images/2023/11/25/202311251649756.png)

![image.png](https://images.wu.engineer/images/2023/11/25/202311251650036.png)
## 6.3 Caching and DAGs
- Log mining example: 
	- Load error messages from a log into memory
	- Then interactively search for various patterns
```Python
# Load file from HDFS (Hadoop distributed file system), then create an RDD
# sc for SparkContext
lines = sc.textfile("hdfs://...")
# Search for the Error line, create a new RDD with Error line
errors = lines.filter(lambda s: s.startwith("Error"))
# Split error line by tab, and extract the third sentence into a new RDD
messages = errors.map(lambda s: s.split("\t")[2])
# Store messages into memory
messages.cache()
# Filter mysql in messages, then count them (from the memory, faster)
messages.filter(lambda s: "mysql" in s).count()
```
- Cache the data can let getting results faster
### Caching
- `cache()`: saves an RDD to memory (in each work node)
- `persist(options)`: can be used to save an RDD to memory, disk, or off-heap memory
- When should we cache or not cache an RDD?
	- When it is expensive to compute and needs to be re-used multiple times
	- If worker nodes have not enough memory, they will evict the "least recently used" RDDs. So, be aware of memory limitations when caching
### Directed Acyclic Graph (DAG)
- Internally, Spark creates a graph (DAG) which represents all the RDD objects and how they will be transformed
- Transformations construct this graph; actions trigger computations on it
### Narrow and Wide Dependencies
- **Narrow Dependencies** are where each partition of the parent RDD is used by at most 1 partition of the child RDD
	- E.g., map, flatMap, filter, contains
- **Wide Dependencies** are the opposite (each partition of parent RDD is used by multiple partition of the child RDD)
	- E.g., reduceByKey, groupBy, orderBy
**窄依赖（Narrow Dependencies）**
- 窄依赖指的是每个父RDD的分区最多被子RDD的一个分区所使用。这种依赖关系意味着计算可以在分区级别上进行，而不需要跨分区的数据交换。
- 例如，`map`、`flatMap`、`filter`、`contains`等操作会产生窄依赖，因为它们在每个输入分区上独立运行，并产生一个输出分区，不需要等待其他分区的数据。

**宽依赖（Wide Dependencies）**
- 宽依赖是指每个父RDD的分区可能被子RDD的多个分区所使用。这种依赖通常涉及到对数据进行聚合或重新组织，需要多个分区之间的数据交换。
- 例如，`reduceByKey`、`groupBy`、`orderBy`等操作会产生宽依赖，因为这些操作需要整合多个分区的数据，可能需要将不同分区的数据汇集到一起进行计算。
![image.png](https://images.wu.engineer/images/2023/11/25/202311251736760.png)

- In the DAG, consecutive narrow dependencies are grouped together as "**stages**"
- **Within stages**, Spark performs consecutive transformations on the same machines
- **Across stages**, data needs to be **shuffled**, i.e. exchanged across partitions, in a process very similar to mapReduce, which involves writing intermediate results to disk
- Minimising shuffling is good practice for improving performance
**DAG和执行阶段**
- 在Spark中，任务的执行通过一个有向无环图（DAG）来表示，DAG中的节点代表RDD，边代表转换操作（即依赖关系）。
- 连续的窄依赖被组织成为一个“阶段”（Stage）。在这些阶段内，Spark可以连续地在同一台机器上执行多个转换，而不需要在节点之间移动数据。
- 不同的阶段之间，由于宽依赖的存在，需要进行数据的“洗牌”（Shuffle），即跨分区交换数据。这个过程类似于MapReduce中的shuffle，并且通常涉及到将中间结果写入磁盘。
**性能优化**
- 由于数据洗牌是一个耗时的过程，涉及到网络传输和磁盘I/O，所以在Spark程序中尽量减少洗牌是提高性能的一个重要实践。这意味着尽可能地利用窄依赖，以及在不可避免需要进行洗牌的宽依赖时，尽量减少需要交换的数据量
![image.png](https://images.wu.engineer/images/2023/11/25/202311251736486.png)
### Lineage and Falut Tolerance
- Unlike Hadoop, Spark does not use replication to allow fault tolerance
	- Spark tries to store all data in memory, not disk. Memory capacity is much more limited than disk, so simply duplicating data is expensive
- **Lineage Approach**: if a worker node goes down, we replace it by a new worker node, and use the graph (DAG) to recompute the data in the lost partition
	- Note that we only need to recompute the RDDs from the lost partition
**容错机制对比**
- 在Hadoop的MapReduce中，容错是通过在磁盘上复制数据来实现的。如果一个数据节点失败，系统可以从副本中恢复数据。
- Spark采取了不同的方法。由于Spark尝试将所有数据保存在内存中以提高速度，而内存资源相比磁盘更有限且成本更高，因此它不依赖于数据的复制来实现容错。
**血统（Lineage）方法**
- Spark的RDD有一种内建的血统记录，即记录了它是如何从其他RDD转换来的。
- 当一个工作节点（Worker Node）发生故障，Spark会启动一个新的工作节点来替代它。
- 利用DAG（有向无环图），Spark能够重新计算丢失的分区数据。DAG记录了RDD之间的所有转换关系，所以Spark可以通过血统信息追溯到原始的数据源，并且只重新计算丢失分区的RDD，而不需要重新计算整个数据集。
- 这种方法效率很高，因为它避免了不必要的数据复制，并且只在数据丢失时才重新计算数据。
## 6.4 DataFrames and Datasets
### DataFrames
- A DataFrame represents a table of data, similar to tables in SQL, or DataFrames in pandas
- Compared to RDDs, this is a higher level interface, e.g. it has transformations that resemble SQL operations
	- DataFrames (and DataSets) are the recommended interface for working with Spark - they are easier to use than RDDs and almost all tasks can be done with them. While only rarely using the RDD functions
	- However, all DF operations are still ultimately compiled down to RDD operation by Spark
#### Example
- Read data from a CSV file
```Python
flightData2015 = spark \
					  .read \
					  .option("inferSchema", "true") \
					  .option("header", "true") \
					  .csv("./2015-summary.csv")
```
- Sorts by 'count' and output the first 3 rows (action)
```Python
flightData2015.sort("count").take(3)
```
![image.png](https://images.wu.engineer/images/2023/11/25/202311251744301.png)
#### Transformations
- An easy way to transform DF is to use SQL queries. This takes in a DF and returns a DF (the output of the query)
```Python
flightData2015.createOrReplaceTempView("flight_data_2015")
maxSql = spark.sql("""
SELECT DEST_COUNTRY_NAME, sum(count) as destination_total
FROM flight_data_2015
GROUP BY DEST_COUNTRY_NAME
ORDER BY sum(count) DESC
LIMIT 5
""")
maxSql.collect()
```
- We can also run the exactly the same query as follows
```Python
from pyspark.sql.functions import desc
flightData2015\
.groupBy("DEST_COUNTRY_NAME")\
.sum("count")\
.withColumnRenamed("sum(count)", "destination_total")\
.sort(desc("destination_total"))\
.limit(5)\
.collect()
```
- Generally, these transformation functions (`groupBy`, `sort`...) take in either strings or "column objects", which represent columns
	- For example, "desc" here returns a column object
### Datasets
- Datasets are similar to DF, but are type-safe
	- In Spark, DF is just an alias of Dataset[row]
	- However, Datasets are not available in Python and R, since these are dynamically typed language
```Python
case class Flight(DEST_COUNTRY_NAME: String, ORIGIN_COUNTRY_NAME: String, count: BigInt)
val flightsDF = spark.read.parquet("/mnt/defg/flight-data/parquet/2010-summary.parquet/")
val flights = flightsDF.as[Flight]
flights.collect()
```
- The Dataset `flights` is type safe - its type is the "Flight" class
- Now when calling `collect()`, it will also return objects of the "Flight" class, instead of Row objects

# 7 - Spark II
## 7.1 Spark SQL
- Unifies Spark components and permits abstraction to DF/Datasets in Java, Python, R
- Keep track of schema and support optimised relational operations
![image.png](https://images.wu.engineer/images/2023/11/25/202311252231058.png)
### 7.1.1 RDD vs DataFrame
- RDD:
	![image.png](https://images.wu.engineer/images/2023/11/25/202311252231279.png)
	- Instruct Spark how to compute the query
	- The intension is completely opaque to Spark 意图不透明
	- Spark also does not understand the structure of the data in RDDs or the semantics of user functions
- DataFrame
	![image.png](https://images.wu.engineer/images/2023/11/25/202311252232666.png)
	- Tell Spark what to do, instead how to do
	- The code is far more expressive as will as simpler
		- Using a domain specific language (DSL) similar to python pandas
		- Use high-level DSL operators to compose the query
	- Spark can inspect or parse this query and understand our intention, it can then optimise or arrange the operations for efficient execution. Spark 可以检查或解析该查询，并理解我们的意图，然后优化或安排操作以高效执行
![image.png](https://images.wu.engineer/images/2023/11/25/202311252236098.png)
### 7.1.2 Catalyst Optimiser
- Catalyst optimiser takes a computational query and converts it into an execution plan through four transformational phases:
	1. Analysis
	2. Logical optimisation
	3. Physical planning
	4. Code generation
![image.png](https://images.wu.engineer/images/2023/11/25/202311252240055.png)
**Out of context**
1. **分析（Analysis）**：
    - 在这个阶段，Catalyst Optimizer 分析 SQL 查询，并将它转换成一个未优化的逻辑计划。分析过程中会检查查询中引用的表和列是否存在，数据类型是否匹配，以及解析函数调用等。这一步通常包括将查询中的表和列名与系统目录（如Hive Metastore）中的元数据对应起来。
2. **逻辑优化（Logical Optimization）**：
    - 逻辑优化阶段是将分析阶段得到的逻辑计划转换成一个优化的逻辑计划。Catalyst 应用一系列规则来优化查询，如谓词下推、投影剪裁、子查询展开、常数折叠等。
3. **物理计划（Physical Planning）**：
    - 在物理计划阶段，优化器将逻辑计划转换成一个或多个物理计划。这个过程也称为物理计划生成。Catalyst 使用代价模型来比较不同的物理计划，并选择一个代价最低（例如，预计会用最少资源执行）的计划作为最终的执行计划。
4. **代码生成（Code Generation）**：
    - 在最后的代码生成阶段，Catalyst 会将选定的物理计划转换成可以在 JVM 上执行的高效字节码。这通过使用名为“Whole-Stage Code Generation”的技术实现，它可以有效地将整个查询阶段的计算合并成单个函数，减少了虚拟机的调用开销。
#### Example
![image.png](https://images.wu.engineer/images/2023/11/25/202311252240834.png)


## 7.2 Machine Learning with Spark ML
### 7.2.1 Problem Setup
#### Classification
![image.png](https://images.wu.engineer/images/2023/11/25/202311252259679.png)
- **Classification:** Categorise samples into classes, given training data
#### Regression
![image.png](https://images.wu.engineer/images/2023/11/25/202311252301904.png)
**Regression**: predict *numeric* labels, given training data
### 7.2.2 Typical ML Pipeline
![image.png](https://images.wu.engineer/images/2023/11/25/202311252303533.png)
### 7.2.3 Data Preprocessing
#### Data Missing
- Why is data missing?
	- Information was not collected
	- Missing at random: missing values are randomly distributed. If data is instead missing not at random, then the missing itself may be important information
- How to handle missing values?
	- Delete objects (rows) with missing values
	- Or: fill in the missing values (imputation)
		- E.g. based on the **mean / median** of that attribute
		- Or: by fitting a **regression** model to predict
		- **Dummy variables**: optionally insert a column which is 1 if the variable was missing, and 0 otherwise
```Python
# Regression
from pyspark.ml.feature import Imputer
imputer = Imputer(inputCols=["a", "b"], outputCols=["out_a","out_b"])
model = imputer.fit(df)model.transform(df).show()
```
![image.png](https://images.wu.engineer/images/2023/11/25/202311252316431.png)
#### Categorical Encoding
- Convert **categorical feature** to **numerical features**
- Numerical values are often assigned in a way that represents the ordinal relationship or inherent order among the categories.
	- E.g., the risk rating [Low, Medium, High] will be converted into [0, 1, 2]
- This let us apply algorithms which can handle numerical features (e.g. linear regression)
- This approach may introducing **unwanted numerical relationship**
#### One Hot Encoding
- Convert **discrete feature** to a series of **binary features**
- This method will not give model any **numerical relationship** for this feature
![image.png](https://images.wu.engineer/images/2023/11/25/202311252326976.png)
#### Normalisation
![image.png](https://images.wu.engineer/images/2023/11/25/202311252326173.png)
**Out of syllabus**
在数据预处理中进行归一化（Normalization）是为了调整数值型数据的尺度，使得所有的特征都被统一到一个固定范围内，通常是[0, 1]或者[-1, 1]。归一化的原因和好处包括：
1. **提高收敛速度**：在梯度下降等优化算法中，归一化可以帮助加快收敛速度。如果不同的特征具有不同的尺度，那么优化过程可能会变得很慢，因为小尺度的特征需要更大的权重变化才能在损失函数中产生相同的影响。
2. **消除量纲影响**：归一化可以消除不同特征的量纲影响，使得模型不会因为特征的尺度而偏向于某些特征。
3. **提高算法精度**：某些算法，如K-最近邻（K-NN）和主成分分析（PCA），是基于距离的算法，如果不同的特征有不同的尺度，那么距离计算可能会被尺度大的特征主导，导致模型性能下降。
4. **避免数值计算问题**：过大或过小的数值在计算机中可能会导致数值溢出或下溢，归一化可以避免这些数值问题。
5. **满足模型的假设**：一些模型对数据有特定的假设，例如线性回归和逻辑回归假设所有的特征都是同等重要的，归一化可以帮助满足这些假设。
### 7.2.4 Training & Testing
#### Logistic Regression
##### Sigmoid Function
- The sigmoid function $\sigma(x)$ maps the real numbers to the range (0,1):
$$
\sigma(x) = \frac 1 {1+e^{-x}}
$$
![image.png](https://images.wu.engineer/images/2023/11/25/202311252332802.png)
![image.png](https://images.wu.engineer/images/2023/11/25/202311252334481.png)
#### Training Logistic Regression
![image.png](https://images.wu.engineer/images/2023/11/25/202311252334005.png)
Big Picture: ML involves fitting the **parameters** of a model (here is $w$, $b$) by minimising a **loss/cost function**
Here, the cost function $J$ is Cross Entropy Loss (intuitively: think of the model's predictions as a probability). The closer the prediction probability to the label, the lower the loss value.
### 7.2.5 Evaluation
Example: COVID-19 Antigen Test
- The **predicted label** is the result from the antigen test (antigen is fast but not so precise)
- The **ground truth label** is the result from more precise test (assume it is absolutely correct)
![image.png](https://images.wu.engineer/images/2023/11/25/202311252341024.png)
- 这里预测数据中只有一个1与验证集中的1对应，然而另一个本该呈现阳性的样本预测为阴性。
- 我们可以将预测结果和真实结果做成真值表：
![image.png](https://images.wu.engineer/images/2023/11/25/202311252343670.png)
- 其中，表中的四个区域代表：
	- TN (True Negative): test correct, (test) output negative
	- TP (True Positive): test correct, output positive
	- FN (False Negative): test wrong, output negative
	- FP (False Positive): test wrong, output positive
- 我们可以用这四个数据计算不同的性能指标：
	- Accuracy: fraction of correct predictions, $\frac {TN+TP} {TN+TP+FN+FP}$
	- Sensitivity: fraction of positive cases that are detected, $\frac {TP} {FN+TP}$
	- Specificity: fraction of actual negatives that are correctly identified, $\frac {TN} {TN+FP}$
![image.png](https://images.wu.engineer/images/2023/11/25/202311252348192.png)
### 7.2.6 Pipelines
- Idea: building complex pipeline out of simple building blocks: e.g. encoding, normalisation, feature transformation, model fitting
- Why?
	- Better code reuse: without pipelines, we would repeat a lot of code, e.g., between the training and test pipeline, cross-validation, model varients
	- Easier to perform cross validation, and hyperparameter tuning
### 7.2.7 Building Block: Transformers
- Transformers are for mapping DF to DF
	- Examples: **one hot encoding, tokenisation**
	- Specifically, a Transformer object has a `transform()` method, which performs its transformation
- Generally, these transformers output a new DF which **append** their result to the original DF
	- Similarly, a fitted model (logistic regression) is a Transformer that transform a DF into one with the predictions appended
![image.png](https://images.wu.engineer/images/2023/11/25/202311252353861.png)

### 7.2.8 Building Blocks: Estimator
- **Estimator** is an algorithm which takes in data, and outputs a fitted model. For example, a learning algorithm (the logistic regression object) can be fit to data, producing the trained logistic regression model
- They have a `fit()` method, which returns a Transformer
![image.png](https://images.wu.engineer/images/2023/11/25/202311252355596.png)
### Estimator
- **Estimator** 是一个算法，它可以基于给定的数据集学习或拟合出一些模型参数。换句话说，它是一个学习算法或者任何一个可以拟合或训练数据的对象。
- 在Spark MLlib中，Estimator抽象表示一个学习算法，或者更具体地说，是一个`fit()`方法。当你对一个数据集调用`fit()`方法时，它会产生一个模型，这个模型就是一个Transformer。
- 举个例子，一个用于分类的逻辑回归或者决策树算法，在训练数据上训练完成后，会变成一个Estimator。
### Transformer
- **Transformer** 是一个转换器，它把一个数据集转换成另一个数据集。通常，在机器学习中，转换器用来改变或预处理数据，比如进行归一化、标准化或者使用模型进行预测。
- 在Spark MLlib中，Transformer表示一个`transform()`方法，该方法接受一个DataFrame作为输入并产生一个新的DataFrame作为输出。通常，这个输出会包含预测结果、转换后的特征等。
- 例如，一个训练好的模型，比如逻辑回归模型，可以用作Transformer来对新数据进行预测。
### 7.2.9 Pipeline: Training Time
- A pipeline chains together multiple Transformers and Estimators to form an ML workflow
- Pipeline is an Estimator. When `pipeline.fit()` is called
	- Starting from the beginning of the pipeline
	- For Transformers, it calls `transform()`
	- For estimators, it calls `fit()` to fit the data and returns a fitted model
### 7.2.10 Pipeline: Testing Time
- The output of `pipeline.fit()` is the estimated pipeline model (of type PipelineModel)
	- It is a transformer, and consist of a series of Transformers
	- When its `transform()` is called, each stage's `transform()` method is called
## 7.3 Evaluate Regression Model
- Mean Absolute Error (MAE)
$$
MAE = \frac 1n \sum^n_{i=1}|y_i-\hat {y_i}|
$$
- Mean Squared Error (MSE)
$$
MSE = \frac 1n \sum^n_{i=1}(y_i-\hat {y_i})^2
$$
- Root Mean Squared Error (RMSE)
$$
RMSE = \sqrt {\frac 1n \sum^n_{i=1}(y_i-\hat {y_i})^2}
$$
- R Squared Value
	- The closer to 1, the better the model fits the data
![image.png](https://images.wu.engineer/images/2023/11/25/202311260003386.png)

