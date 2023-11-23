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


