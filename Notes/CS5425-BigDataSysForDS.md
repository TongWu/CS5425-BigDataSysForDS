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