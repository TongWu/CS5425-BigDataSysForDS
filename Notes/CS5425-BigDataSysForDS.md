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
>    - ```
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

# 3 - Hadoop File System

