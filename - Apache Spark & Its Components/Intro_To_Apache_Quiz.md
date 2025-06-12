
## 📘 Apache Spark & HDFS Quiz Questions with Explanations

---

### ✅ QUESTION 1: What is one of the main benefits of Spark's in-memory processing?

◻  Reduced CPU usage  
✅ Reduced I/O operations and faster processing  
◻  Fewer cluster nodes required  
◻  Increased disk storage utilization  

#### 💡 Explanation:
Spark keeps intermediate data in **memory (RAM)** rather than writing to disk, which:  
- Minimizes **disk I/O operations**  
- Speeds up data processing significantly  
This is particularly useful in iterative machine learning and data analytics tasks.

---

### ✅ QUESTION 2: Which of the following languages is NOT supported by Apache Spark?

✅ JavaScript  
◻  Python  
◻  Scala  
◻  Java  

#### 💡 Explanation:
Apache Spark supports **Scala, Java, Python, R, and SQL**, but **not JavaScript**.  
JavaScript is primarily a web development language and not suitable for Spark’s distributed computing model.

---

### ✅ QUESTION 3: Which characteristic of Apache Spark allows it to handle both static and dynamic data?

◻  Dependency on Hadoop  
◻  High reliance on disk storage  
✅ Support for hybrid workloads  
◻  Sequential data processing  

#### 💡 Explanation:
Spark supports **hybrid workloads**, meaning it can process both **batch (static)** and **streaming (dynamic)** data using the same engine, enabling seamless real-time and historical analysis.

---

### ✅ QUESTION 4: What is the primary role of the driver in Spark?

◻  Storing large datasets across clusters  
◻  Performing data computation  
◻  Monitoring worker node health  
✅ Coordinating and scheduling tasks  

#### 💡 Explanation:
The **driver** is the brain of a Spark application. It:  
- Breaks the job into **tasks**  
- Sends them to **executors**  
- **Monitors** the overall execution and manages resources

---

### ✅ QUESTION 5: Which component divides a Spark job into smaller tasks?

◻  Resource Manager  
◻  Executor  
✅ Driver  
◻  Worker Node  

#### 💡 Explanation:
The **Driver** analyzes the job and splits it into **stages and tasks**, assigning them to **executors** for parallel execution.

---

### ✅ QUESTION 6: Where does Spark temporarily store intermediate data for faster computation?

✅ In-memory caching of executors  
◻  In the driver  
◻  On disk  
◻  Within the Resource Manager  

#### 💡 Explanation:
Spark uses **in-memory caching** within **executors** to hold intermediate results, which **avoids repeated computations** and **speeds up performance**.

---

### ✅ QUESTION 7: Which of the following best describes Spark's fault-tolerant feature?

◻  It eliminates the need for backups.  
◻  It relies solely on driver memory.  
◻  It only prevents node failures.  
✅ It tracks computation lineage to recover from failures.  

#### 💡 Explanation:
Spark maintains a **lineage graph** of transformations, allowing it to **recompute lost data** if a failure occurs, instead of restarting the entire job.

---

### ✅ QUESTION 8: What is the purpose of lineage information in RDDs?

✅ To recover data in case of failures  
◻  To speed up data processing  
◻  To store replicas of RDDs for backup  
◻  To transform RDDs into DataFrames  

#### 💡 Explanation:
**Lineage** in RDDs keeps a **record of all transformations** used to derive them. This allows Spark to **rebuild lost partitions** in case of failure.

---

### ✅ QUESTION 9: What differentiates wide transformations from narrow transformations?

✅ Wide transformations require data shuffling across partitions.  
◻  Wide transformations modify the original dataset.  
◻  Wide transformations execute immediately.  
◻  Wide transformations do not support lazy evaluation.  

#### 💡 Explanation:
**Wide transformations** involve **data shuffling** between partitions and are more expensive. Examples include `groupByKey`, `reduceByKey`, and `join`.

---

### ✅ QUESTION 10: What is the purpose of lazy evaluation in RDDs?

◻  To immediately execute transformations  
✅ To build an optimized execution plan before processing data  
◻  To reduce memory consumption by avoiding caching  
◻  To allow real-time data processing  

#### 💡 Explanation:
Lazy evaluation allows Spark to **delay execution** of transformations until an **action** is called. This helps in **optimizing the execution plan** and avoiding unnecessary computations.

---

