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

# Db2 Products -
## 1. Db2 for z/OS -
- Db2 for z/OS is the mainframe version of Db2 that runs on the z/OS operating system. I
- t is designed for high-volume transaction processing, high availability, scalability, security, and reliability.
- It is widely used in industries such as banking, insurance, telecommunications, and government.

## 2. Db2 for Linux, UNIX, and Windows (Db2 LUW)
- Db2 LUW is a distributed database management system that runs on Linux, UNIX, and Windows platforms.
- It provides support for online transaction processing (OLTP), analytical workloads, and enterprise applications. It can be deployed in both on-premises and cloud environments.

## 3. Db2 Warehouse
- Db2 Warehouse is a data warehousing solution designed for large-scale analytics and business intelligence workloads.
- It provides advanced query performance, data compression, parallel processing, and support for analytical applications.

## 4. Db2 Warehouse on Cloud
- Db2 Warehouse on Cloud is a fully managed cloud-based data warehouse service.
- It provides scalable storage and computing resources, reduces infrastructure management requirements, and supports advanced analytics in cloud environments.

## 5. Db2 Community Edition
- Db2 Community Edition is a free version of Db2 intended for learning, development, testing, and small-scale production environments.
- It includes core database functionality and allows users to gain experience with Db2 technology.

## 6. Db2 Advanced Edition
- Db2 Advanced Edition is an enterprise-level database solution that includes advanced features for performance optimization, high availability, workload management, security, and scalability. I
- t is designed for mission-critical business applications.

# Db2 Architecture -
- Db2 follows a client-server architecture in which client applications communicate with the Db2 database server to access and manage data.
- The architecture consists of several components that work together to provide efficient data processing, storage management, and high-performance database operations.

## Client Layer -
- The client layer consists of applications that connect to the Db2 database server.
- Applications are linked with the Db2 client library and communicate with the server to submit SQL requests and receive results.

#### Local Client Communication -
- When the application and Db2 server reside on the same machine, communication occurs through:
    - Shared Memory
    - Semaphores
- This method provides fast communication because network protocols are not required.

#### Remote Client Communication -
- When the application and Db2 server reside on different machines, communication occurs through network protocols such as:
   - TCP/IP
   - NPIPE (Named Pipes)
- These protocols enable applications to access databases remotely.

## Db2 Server -
- Db2 Server is responsible for processing client requests and managing database operations.
- It contains several internal components that work together to provide efficient database services. All activities within the server are controlled by Engine Dispatchable Units (EDUs).

### Engine Dispatchable Units (EDUs)
- Engine Dispatchable Units (EDUs) are the fundamental processing units within Db2. They are implemented as threads and perform various database tasks.
- Thread is the smallest unit of execution within a process. It performs a specific task independently while sharing the same memory and resources of the process.

##### Agents -
- Agents are the most common type of EDU. Db2 agents perform most of the SQL and XQuery processing required by applications.
- They receive requests from clients, execute database operations, and return the results.
- Apart from Db2 Agents, the most important and commonly used EDUs are Page Cleaners and Prefetchers.

##### Subagents -
- Subagents are helper processing units assigned to support agents in handling client requests.
- Multiple subagents may be assigned when server contains multiple processors and database operates in a partitioned environment.
- In a Symmetric Multiprocessing (SMP) environment, multiple subagents can execute tasks simultaneously by utilizing multiple processors, thereby improving performance through parallel processing.

##### Pooling Algorithm -
- Pooling Algorithm in Db2 is a mechanism used to manage Agents and Subagents efficiently.
- Instead of creating a new EDU (thread) for every client request and destroying it after use, Db2 keeps a pool of reusable EDUs.
- It improves performance as requests are processed faster because EDUs are already available.
- Creating and destroying threads repeatedly is expensive because it consumes: CPU resources, Memory, Time

##### Buffer Pools -
- Buffer pool is a memory area used to temporarily store database pages, including:
    - User data pages: store the actual table data
    - Index pages: store index entries used for fast data retrieval
    - Catalog pages: store metadata about database objects such as tables, columns, indexes, and tablespaces.
- Buffer pools improve database performance because accessing data from memory is significantly faster than accessing data from disk storage.

##### Prefetchers -
- Prefetchers are background EDUs responsible for moving data from disk storage into the buffer pool before applications request it.
- The purpose of prefetching is to reduce application wait time, improve query performance, and increase data access efficiency by loading data into memory before it is requested.
- Applications send asynchronous read-ahead requests to prefetchers through a common prefetch queue. Prefetchers retrieve the required pages and place them into the buffer pool in advance.
- When prefetchers receive requests, they perform operations such as:
    - Big-block reads: reads many pages in a single operation
    - Scatter-read operations: reads multiple pages from disk and places them into different locations in the Buffer Pool in a single operation.
- These techniques allow data pages to be transferred efficiently from disk into memory.
- If data is distributed across multiple disks, prefetchers can retrieve data simultaneously from several disks. This process, known as data striping, improves I/O performance and reduces data retrieval time.

##### Page Cleaners -
- Page Cleaners are background EDUs responsible for moving modified data pages from the buffer pool back to disk storage.
- Page cleaners identify changed pages, write modified pages to disk, maintain free space in buffer pools, and support prefetcher operations for efficient data management.
- Page cleaners operate independently of application agents and perform their tasks in the background.
- Without page cleaners, application agents would be required to perform all disk write operations, reducing overall system performance.

# Database Storage Components
- Db2 stores and manages data using a hierarchy of logical and physical storage structures. These components work together to organize, store, and retrieve data efficiently.

## Database
- Database is a logical collection of related database objects such as tables, indexes, views, and tablespaces.
- It serves as a container for organizing and managing related data within the Db2 environment.

## Tablespaces
- Tablespace is a storage structure within a database that physically stores table data.
- Tablespaces provide a logical grouping of storage and help manage how data is stored on disk.

## Tables
- Table is a database object that stores actual user data in the form of rows and columns.
- Each row represents a record, and each column represents an attribute of that record.

## Indexes
- Index is a database object that provides an efficient access path to data stored in tables. 
- Indexes improve query performance by allowing Db2 to locate required rows quickly without scanning the entire table.

Database
    ↓
Tablespace
    ↓
Table
    ↓
Rows and Columns
