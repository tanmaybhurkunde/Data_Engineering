# Hadoop vs Spark Ecosystem Comparison

| Feature | Hadoop Ecosystem (MapReduce) | Spark Ecosystem |
| --- | --- | --- |
| **Processing model** | Disk-based batch jobs | In-memory + batch + streaming |
| **Speed** | Slower (writes intermediate results to disk) | Much faster (keeps data in memory) |
| **Ease of use** | Complex Java APIs, verbose | High-level APIs (PySpark, SQL) |
| **Workloads** | Batch only | Batch, streaming, ML, graph |
| **Storage** | HDFS | Works with HDFS, S3, Delta Lake, etc. |
| **Modern adoption** | Declining | Dominant in data engineering |
