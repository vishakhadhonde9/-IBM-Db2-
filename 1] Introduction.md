# Overview of Db2 -
- Db2 was introduced by IBM in 1983 as a relational database management system.
- Despite being over four decades old, it is still widely used because of its reliability, security, scalability, and ability to handle mission-critical workloads.
- Db2, first introduced in 1983, continues to evolve with new versions, enhanced security, improved performance, cloud integration, and AI-assisted database management features, making it a mature and actively maintained database platform.

# Db2 -
- Db2 is IBM's enterprise-grade relational database management system (RDBMS) that stores and manages data securely, reliably, and efficiently.
- The "2" in Database 2 refers to IBM's second generation of database software, which moved from the hierarchical database model to the relational database model.

# Features of Db2 -
### 1. AI-Powered Functionality -
- Db2 incorporates Artificial Intelligence (AI) capabilities to simplify database management and query processing.
- AI-driven features help users optimize SQL queries, automate administrative tasks, and improve overall database efficiency with reduced manual intervention.

### 2. Machine Learning-Based Optimization
- Db2 uses Machine Learning (ML) algorithms to analyze workload patterns and system behavior.
- These algorithms help improve query performance, optimize resource utilization, and enhance database efficiency by learning from historical operations.

### 3. Column Store Technology
- Db2 supports column-organized storage, where data is stored by columns rather than rows.
- This approach improves analytical query performance by allowing the database to access only the required columns instead of scanning entire rows, thereby reducing I/O operations and processing overhead.
- **Row-Based Storage**
    
      Employee1: 101 Tom 50000
      Employee2: 102 Jerry 60000

- **Column-Based Storage**

      EMP_ID : 101 102
      NAME   : Tom Jerry
      SALARY : 50000 60000

- If a query needs only salary information:

      SELECT SALARY FROM EMPLOYEE;

- Db2 reads only the SALARY column instead of the entire row.

### 4. Data Skipping
- Data skipping is a performance optimization feature that enables Db2 to automatically exclude irrelevant data blocks during query execution.
- By avoiding unnecessary data scans, Db2 significantly reduces query processing time and improves system performance.

### 5. Common SQL Engine
- Db2 provides a common SQL engine across its various platforms and products.
- This allows SQL statements to be written once and executed consistently across different Db2 environments, improving portability, application compatibility, and ease of development.

### 6. Support for Multiple Data Types
- Db2 can manage and process various types of data, including:
  - Structured data
  - Relational data
  - Semi-structured data
  - Unstructured data
- This capability enables organizations to store and analyze diverse datasets within a single database platform.

### 7. High Availability and Disaster Recovery (HADR)
- Db2 provides High Availability and Disaster Recovery (HADR) features to ensure continuous database operation and data protection.
- Through replication and failover mechanisms, Db2 minimizes downtime and safeguards data against hardware failures, software issues, and site-level disasters.

### 8. Scalability
- Db2 is designed to scale according to organizational requirements. It supports both vertical scaling (adding more CPU, memory, or storage resources) and horizontal scaling (adding additional servers).
- Cloud integration further enables organizations to dynamically adjust resources based on workload demands.

### 9. Table Partitioning
- Db2 supports table partitioning, which divides large tables into smaller, manageable partitions. 
- This improves query performance, facilitates parallel processing, enhances manageability, and allows efficient utilization of computing resources across multiple servers.
