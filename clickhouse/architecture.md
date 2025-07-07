Link to source https://clickhouse.com/docs/development/architecture

### GENERAL ARCHITECTURE

* What is the primary design goal of ClickHouse?
(Hint: speed, OLAP workloads, real-time analytics)

* What kind of query patterns is ClickHouse optimized for?
(e.g., short reads? full-table scans? many writes?)

* How does ClickHouse differ from transactional (OLTP) databases in design priorities?

* What is the role of "read-only compressed columnar storage" in performance? 

### STORAGE LAYER
* What is a “part” in ClickHouse, and how is it related to a table?

* How are parts organized on disk? What is the role of partitions?

* What happens during a merge operation? Why is it important?

* What trade-off does ClickHouse make by avoiding in-place updates?

* Where are parts stored physically by default?

* What does it mean that data is immutable in ClickHouse?

### ENGINE LAYER

What is a table engine in ClickHouse? Name at least 3 engines and what they do.

What is MergeTree? Why is it the most used engine?

How does ClickHouse allow pluggable table engines without modifying the core system?

* What are the advantages of separating storage and compute at the engine level?



### QUERY EXECUTION

What are “blocks” in ClickHouse query processing?

Why does ClickHouse use vectorized execution? What does it mean concretely?

What is a pipeline in ClickHouse query execution?

How does ClickHouse ensure that query execution is CPU-cache efficient?

What are “streams” and how are they related to blocks?

### MULTITHREADING & PARALLELISM

How does ClickHouse make use of multiple CPU cores during query execution?

Which parts of query execution are parallelized? Which are single-threaded?

What mechanism ensures efficient multithreaded merge operations?

### DISTRIBUTED PROCESSING

What is the role of Distributed tables in ClickHouse?

How does ClickHouse handle data sharding and replication?

Does ClickHouse support distributed JOINs and GROUP BY? What’s the performance cost?

What happens if one replica is unavailable in a replicated setup?

### FAULT TOLERANCE & CONSISTENCY

How does ClickHouse handle data consistency in case of crash or power failure?

What trade-offs does ClickHouse make in terms of ACID properties?

How does ClickHouse replication work? Does it guarantee strong consistency?

### OPTIONAL ADVANCED


What are MergeTree mutations and how are they executed?

How is background work scheduled in ClickHouse (e.g. merges, mutations)?

What’s the role of ZooKeeper in replicated MergeTree engines?

### Meta


What design choices in ClickHouse make it particularly fast for analytical queries?

What performance bottlenecks is ClickHouse architected to avoid?

What assumptions about the workload does ClickHouse make to optimize performance?