
# 🧠 Introduction to YARN (Yet Another Resource Negotiator)



---

## 🚀 What is YARN?

YARN stands for **Yet Another Resource Negotiator**. It’s the **resource manager** of the Hadoop ecosystem — like the central brain that decides who gets what and when in a big Hadoop cluster.

**Think of YARN like an air traffic controller:**
- Jobs are airplanes.
- Nodes are runways.
- YARN decides which jobs (planes) go to which nodes (runways), ensuring efficient, safe operation.

---

## 🔑 Key Features of YARN

| Feature                    | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| 🎯 Resource Management     | Dynamically allocates resources (CPU, memory) based on job requirements     |
| 🗓️ Job Scheduling           | Plans when and where jobs run across the cluster                            |
| 📈 Scalability              | Can grow to support thousands of nodes and tasks                            |
| 🔁 Multi-framework Support | Works with tools like MapReduce, Spark, Tez, Flink, etc.                    |

---

## 🧱 YARN Architecture – Who Does What?

YARN has three main components:

### 🏢 **1. Resource Manager (RM)**

- The **master daemon** – runs on one node.
- Accepts job requests and decides resource allocation.
- Coordinates job scheduling across the cluster.
- Keeps track of:
  - Available memory/CPU on all nodes.
  - Health of nodes.
  - Data locality.

### 🛠️ **2. Node Manager (NM)**

- Runs on **every node** in the cluster.
- Reports resource usage to the Resource Manager.
- Launches **containers** to run tasks.
- Monitors CPU, memory, disk usage on its node.

### 📦 **3. Application Master (AM)**

- Created **per job**.
- Responsible for **managing the life cycle** of a specific application.
- Requests containers from Resource Manager.
- Coordinates with Node Managers to run tasks.

---

## 🔁 How YARN Works – Step by Step

1. **Client Submits a Job**
   - Example: Running a Hive query or Spark job.
   - The job is submitted to the **Resource Manager**.

2. **Resource Allocation**
   - RM checks which nodes are healthy and available.
   - Considers **data locality** (to avoid unnecessary data movement).

3. **Launching Application Master**
   - RM starts an **Application Master** on a suitable node.
   - AM requests required containers to complete the job.

4. **Task Execution in Containers**
   - Node Managers launch containers to perform tasks.
   - Each container runs part of the application (like mapper or reducer).

5. **Real-Time Monitoring**
   - Node Managers report health and progress to RM.
   - RM reallocates if tasks fail or nodes go offline.

---

## 🎯 Real-World Scenario

**Scenario:** An e-commerce company wants to analyze clickstream logs from millions of users.

- Logs are stored in HDFS.
- The client submits a Spark job using YARN as the resource manager.
- YARN:
  - Allocates memory and CPU to each Spark executor.
  - Starts Application Master for this Spark job.
  - Distributes the work among containers.
  - Reschedules failed tasks if a node goes down.

---

## 🖼️ Diagram: YARN Architecture Overview

```
+---------+       +---------------------+       +--------------------+
|  Client | --->  |  Resource Manager   | <---> |  Node Managers     |
+---------+       |   (Central Brain)   |       |  (Run on all nodes)|
                  +----------+----------+       +---------+----------+
                             |                            |
                  +----------v----------+       +-------- v --------+
                  | Application Master  |       |   Containers      |
                  | (1 per application) |       | (Run tasks on NMs)|
                  +---------------------+       +-------------------+
```

---

![YARN Diagram](https://data-flair.training/blogs/wp-content/uploads/sites/2/2018/11/YARN-Architecture.png)

---

## 🛠️ Benefits of YARN

- ✅ **Flexible**: Supports multiple data processing tools.
- ✅ **Efficient**: Utilizes cluster resources better than traditional systems.
- ✅ **Scalable**: Can scale to thousands of nodes.
- ✅ **Fault Tolerant**: Can detect node failure and rerun tasks elsewhere.

---

## ⚠️ Limitations of YARN

| Limitation             | Explanation                                                              |
|------------------------|--------------------------------------------------------------------------|
| 🐢 Complexity           | More components = more points of failure                                |
| 💽 Overhead             | Each job runs its own Application Master, which adds overhead           |
| 🧠 Requires Expertise   | Configuration tuning is needed to optimize for performance              |

---

## 🧠 Summary

- YARN manages **who runs what, where, and how** in Hadoop.
- It separates **resource management** from **job execution**.
- Works with modern tools like Spark, Hive, Tez, etc.
- Essential for running large-scale data jobs efficiently.

> 🔑 *Mastering YARN helps you manage Big Data like a pro!*

---

