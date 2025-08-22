---
Title: Data Base Management System Lecture 15
Status: 
marker: 
tags: 
Date: 2024.10.16
Time: 15:19
---
## NOSql

Data can be categorized into various forms:
- **Tabular Data**: This is structured data, stored in a tabular form (rows and columns), typically found in relational databases.
- **Structured or Semi-Structured Data**: This includes formats like XML, JSON, or CSV where data is structured but may not strictly adhere to tabular formats.
- **Unordered Data**: Data that does not follow any specific order and can include multimedia files, logs, or NoSQL data formats.

For different types of data formats, we often require distinct storage methods or databases to handle them efficiently. For example:

- If you're storing **Instagram posts** where some posts don't have captions, you would have blank fields for the caption in structured databases.
- In such cases, it’s more efficient to use **key-value pairing** (common in document databases like NoSQL), where each document only stores the necessary data (e.g., resolution size, encoding, pixels, framerate, etc.), saving storage space.

### NoSQL Databases
- **NoSQL databases** are used when we don't need **ACID properties** (Atomicity, Consistency, Isolation, Durability) that traditional relational databases offer.
- These databases are flexible and allow for the storage of unstructured or semi-structured data.
- Commonly used in cases where horizontal scaling and flexibility are prioritized, such as social media platforms or applications handling large volumes of varying data formats.

---

### RDBMS Characteristics

**Relational Database Management Systems (RDBMS)** follow strict rules for storing, managing, and accessing structured data. Here are the key characteristics:

1. **Data Stored in Tables and Columns**:
   - In an RDBMS, data is stored in **tables** that consist of rows (records) and columns (fields).
   - Each table has a well-defined schema, and the data must conform to this structure.

2. **Relationships Represented by Data**:
   - RDBMS allows for establishing relationships between different tables through **primary keys** (unique identifiers for rows) and **foreign keys** (to refer to primary keys in other tables).
   - These relationships maintain **data integrity** and **referential integrity**.

3. **Data Manipulation Language (DML)**:
   - DML is used for querying and modifying data within the database.
   - Commands include **SELECT**, **INSERT**, **UPDATE**, and **DELETE** for performing operations on the data.

4. **Data Definition Language (DDL)**:
   - DDL deals with defining the structure of the database, including **CREATE**, **ALTER**, **DROP**, and **TRUNCATE** commands.
   - These commands control the schema and organization of the tables and relationships.

5. **Transactions**:
   - RDBMS supports **transactions** that ensure multiple operations are executed safely, following the **ACID properties**:
     - **Atomicity**: All operations in a transaction are completed successfully, or none are.
     - **Consistency**: Data remains consistent before and after the transaction.
     - **Isolation**: Transactions are executed independently without interfering with each other.
     - **Durability**: Once a transaction is committed, the data is saved permanently.

6. **Abstraction from Physical Layer**:
   - RDBMS abstracts the underlying physical layer, so users and applications don’t need to worry about the storage details. This abstraction allows:
     - **Logical data independence**: Applications specify **what** data they need, not **how** it is stored or accessed.
     - **Physical layer independence**: The storage system or hardware can be changed without requiring modifications to the applications.

7. **Indexes to Support Queries**:
   - RDBMS uses **indexes** to optimize query performance. Indexes are created on columns to allow faster searching and retrieval of data.
   - Proper indexing improves database performance, especially for large datasets.

8. **In-Memory Databases**:
   - Some RDBMS systems utilize **in-memory databases**, where data is stored in the main memory (RAM) instead of on disk, significantly improving read and write performance.
   - In-memory databases are particularly useful for high-speed, real-time applications where performance is critical.
### ACID Properties

The **ACID properties** are a set of four key properties that ensure reliable processing of database transactions in a Relational Database Management System (RDBMS). These properties are:

1. **Atomicity**:
   - Ensures that each transaction is treated as a single unit of work. Either **all** operations within the transaction are completed successfully, or **none** are.
   - Example: If you're transferring money between bank accounts, both the debit from one account and the credit to another account must occur, or neither will happen.

2. **Consistency**:
   - Guarantees that a transaction will bring the database from one valid state to another, ensuring that data integrity is maintained.
   - Example: Before and after a transaction, all data must follow the defined rules (e.g., constraints, triggers) of the database.

3. **Isolation**:
   - Ensures that multiple transactions can occur simultaneously without interfering with each other.
   - Example: If two users are accessing the same account balance, the system ensures their transactions don’t cause conflicts.

4. **Durability**:
   - Ensures that once a transaction is committed, the changes are permanent, even if there is a system crash.
   - Example: Once a financial transaction is completed, it remains in the system even if a power failure occurs.

---

### What is NoSQL?

**NoSQL** stands for **Not Only SQL**. It is a broad category of databases that do **not** follow the traditional relational database model (RDBMS). NoSQL databases are designed to handle:
- Large, unstructured, or semi-structured data sets.
- Horizontal scaling for large-scale distributed systems.
- High performance for real-time web applications.

#### Key Characteristics of NoSQL Databases:
- **No Relational Model**: NoSQL databases don't adhere to the relational table-based structure of traditional RDBMS.
- **Scalable**: Often horizontally scalable, meaning they can handle large amounts of data by adding more servers.
- **Flexible Data Models**: They support document-based, key-value, graph, or wide-column stores, which allows more flexibility in data structures.
- **No Fixed Schema**: NoSQL databases are schema-less, meaning they don't require a predefined schema for the data.
- **Big Data Handling**: Often used for handling vast amounts of diverse and complex data (e.g., social media, IoT, etc.).

**NoSQL** is an umbrella term that includes:
- **Document Stores**: MongoDB, CouchDB
- **Key-Value Stores**: Redis, DynamoDB
- **Wide-Column Stores**: Cassandra, HBase
- **Graph Databases**: Neo4j, ArangoDB

NoSQL databases are particularly useful for applications where:
- The data structure is flexible and can evolve over time.
- Large-scale data is processed in real-time, such as with social media platforms, online gaming, and big data applications.

---

### What is Big Data?

**Big Data** refers to extremely large and complex data sets that cannot be managed, processed, or analyzed using traditional data processing techniques. These data sets grow exponentially and come from a variety of sources, such as social media, IoT devices, transactions, sensors, and more.

The three defining characteristics of Big Data, often referred to as the **Three V’s**, are:

1. **Volume**:
   - Refers to the **size** of the data. Big Data involves data sets that are too large to be processed by traditional database systems.
   - Example: Terabytes to petabytes of data generated by social media, financial transactions, or sensors.

2. **Velocity**:
   - Refers to the **speed** at which data is generated, collected, and processed. In the age of IoT and real-time applications, data is often generated at high speeds.
   - Example: Real-time data from sensors, social media updates, stock market transactions.

3. **Variety**:
   - Refers to the **different types** of data. Big Data encompasses structured, semi-structured, and unstructured data. It can come in formats like text, video, images, log files, and more.
   - Example: A combination of emails, social media posts, and transactional data stored in different formats.

Some researchers also mention a fourth "V":
- **Veracity**: Refers to the **uncertainty** or **inconsistency** of data. With the increase in data sources, ensuring the quality and accuracy of data becomes more challenging.

---

### Summary

- **ACID Properties** ensure reliable database transactions in RDBMS systems, emphasizing consistency, reliability, and isolation.
- **NoSQL** databases offer flexibility and scalability for large, unstructured, or semi-structured data and are commonly used in Big Data applications.
- **Big Data** refers to massive data sets characterized by high **Volume**, **Velocity**, and **Variety**, requiring specialized tools and approaches for processing and analysis.

This note should give you a strong understanding of how ACID properties relate to traditional databases and why NoSQL databases and Big Data concepts have emerged to handle modern data challenges.

### Limitations of RDBMS

While **Relational Database Management Systems (RDBMS)** are powerful and widely used for structured data, they come with certain limitations, especially in the context of modern data requirements such as big data, unstructured data, and high-speed processing. Here are some of the major limitations of RDBMS:

1. **Impedance Mismatch**:
   - This refers to the difference between the **relational model** of databases and the **object-oriented model** of modern programming languages. 
   - In object-oriented languages, data is represented as objects, but relational databases store data in tables. Converting objects into tables (and vice versa) leads to complexity and performance issues.
   - Example: Handling nested objects or collections of data (common in programming) is cumbersome in a relational model.

2. **Unsuitable Data Model for Certain Domains**:
   - The relational model, with its rigid schema of tables, columns, and rows, is **unsuitable for certain data models**, particularly those that involve highly connected or hierarchical data (e.g., social networks or geographic data).
   - Example: A graph-based database like **Neo4j** is much more suitable for handling interconnected data than an RDBMS.

3. **Difficult Schema Evolution Due to Inflexible Data Model**:
   - RDBMS schemas are **rigid**. Any change in the structure of a table (like adding new columns or changing data types) often requires **migration** and can lead to **downtime**.
   - This makes it difficult to accommodate changes when the application's requirements evolve over time.
   - Example: If you need to change the data model or introduce new fields, it can involve a lot of work to update existing records, tables, and relationships.

4. **Weak Distributed Availability Due to Poor Horizontal Scalability**:
   - Traditional RDBMS systems are not designed for **horizontal scaling** (scaling across multiple servers). Most RDBMS rely on **vertical scaling**, which means upgrading the power of a single server.
   - This makes it hard for RDBMS to handle **distributed systems** or applications with a global user base where data needs to be replicated and accessed across different regions.
   - Example: Applications like Facebook or Google need to scale horizontally across thousands of servers, which is difficult to achieve with a traditional RDBMS.

5. **Performance Hit with Large Data Sets**:
   - As data volume grows, the performance of RDBMS can degrade significantly, especially in cases where there are complex **JOIN** operations, **indexes**, or heavy **write** operations.
   - Handling **big data** or **real-time data processing** is challenging with RDBMS because it cannot scale efficiently without hitting performance bottlenecks.
   - Example: An RDBMS may struggle to efficiently handle large-scale analytics or data-intensive applications like IoT or social media platforms with massive amounts of unstructured data.

---

### Summary of RDBMS Limitations:

- **Impedance Mismatch**: Difficulty bridging the gap between object-oriented programming and relational databases.
- **Unsuitable Data Model**: Rigid tabular data models are not suitable for every domain, especially those with hierarchical or graph-based data.
- **Inflexible Schema Evolution**: Difficult to adapt and evolve the schema over time without significant rework and downtime.
- **Poor Horizontal Scalability**: Traditional RDBMS systems struggle to scale out across multiple servers in distributed environments.
- **Performance Issues**: RDBMS performance degrades with large data sets, especially when handling complex queries or heavy write operations.

In contrast to these limitations, modern **NoSQL databases** are designed to address many of these challenges, especially when it comes to handling big data, schema flexibility, and horizontal scaling.

### Why RDBMS Are Not Suitable for Big Data in the Context of the Internet

As the internet has grown, so has the volume, variety, and velocity of data generated. This evolution, often referred to as **Big Data**, has exposed several limitations of traditional **Relational Database Management Systems (RDBMS)**. While RDBMS is effective for structured, small-to-medium scale datasets, it struggles to manage the characteristics and demands of Big Data effectively. Here’s why:

### 1. **Rigid Schema (Inflexible Structure)**

- **Big Data** on the internet is often **unstructured** or **semi-structured** (e.g., social media posts, multimedia files, logs, sensor data), which doesn't fit well into the rigid **schema-based** structure of RDBMS.
- **RDBMS** requires a predefined **schema**, meaning the structure of tables, columns, and relationships must be defined upfront. In contrast, **Big Data** needs a more flexible schema that can evolve with time, and the unstructured data cannot easily conform to this tabular model.
  
**Example**: Social media platforms like Twitter generate posts with different attributes (text, images, videos, links). Storing all these data types in a structured RDBMS table would require complex table structures or wasted storage due to blank fields for non-relevant data types.

### 2. **Scalability Issues (Poor Horizontal Scaling)**

- Big Data on the internet requires **horizontal scalability** — the ability to add more servers to handle increasing loads. Traditional RDBMS systems are designed to scale **vertically** (upgrading a single machine’s capacity) rather than horizontally (spreading the load across multiple servers).
  
- In an internet-driven world, data is generated at a massive scale, and a single server will eventually become a bottleneck in RDBMS-based systems. To distribute this workload efficiently, **NoSQL** databases are preferred as they are designed to scale horizontally across distributed servers.

**Example**: Platforms like Facebook or Google handle petabytes of data daily, which requires scaling out across thousands of servers, something RDBMS is not efficient at doing.

### 3. **Handling High Volume, Variety, and Velocity (The Three V’s)**

- **Volume**: The internet generates data at a scale that RDBMS cannot efficiently manage. From social media interactions to IoT sensors, the sheer volume of data (ranging from terabytes to petabytes) overwhelms the storage and processing capacity of traditional databases.
  
- **Variety**: Big Data is not just structured (like text or numbers); it includes **unstructured data** like images, videos, and JSON documents, which RDBMS systems struggle to handle due to their rigid structure.
  
- **Velocity**: The speed at which data is generated and needs to be processed on the internet (think of real-time data from stock markets, streaming data from sensors) is not easily manageable by traditional RDBMS, which often requires transactional consistency and complex indexing.

**Example**: Streaming services like Netflix generate vast amounts of data in real-time. These services need to store user interactions, movie recommendations, and streaming performance data in milliseconds, a requirement that traditional RDBMS struggles to meet.

### 4. **Performance Bottlenecks with Massive Data Sets**

- With **Big Data**, performing complex queries and **JOIN operations** over massive data sets in RDBMS causes significant performance degradation. As the size of the database grows, so do the time and resources required for maintaining **indexes**, **sorting**, and **query optimization**.

- Big Data analytics often involve complex aggregations, filtering, and sorting over unstructured datasets, which RDBMS systems find hard to handle without substantial performance issues.

**Example**: If you need to run analytics over a large dataset containing billions of web logs, RDBMS may take too long due to the complexity of joins and indexing, making it impractical for real-time analysis.

### 5. **High Write Throughput and Distributed Availability**

- In an internet-based context, systems need to handle **high write throughput** (e.g., millions of writes per second from user interactions) and ensure **distributed availability** across global data centers. RDBMS systems were not designed for this level of write performance.
  
- NoSQL databases like **Cassandra**, **MongoDB**, and **DynamoDB** are built to handle such workloads efficiently, providing high availability and partition tolerance by replicating data across distributed servers globally.

**Example**: E-commerce platforms like Amazon need to handle millions of transactions, user reviews, and product inventory updates per second. Ensuring global data availability with low-latency access is something that NoSQL systems are better equipped to handle compared to traditional RDBMS.

### 6. **Cost and Resource-Intensive**

- Scaling an RDBMS to handle Big Data requires investing in **high-end hardware** (vertical scaling) and complex configurations to maintain performance and availability. In contrast, **NoSQL** databases offer more cost-effective scaling by using commodity hardware for **horizontal scaling**.
  
- For internet-based Big Data platforms, operational costs, including storage, computation, and performance optimization, can be reduced with more scalable NoSQL systems.

**Example**: Companies like Uber or Airbnb need a cost-effective solution to store massive amounts of user and ride data. Using an RDBMS would require expensive infrastructure upgrades, while a NoSQL database can be deployed across cheaper, distributed servers.

### Conclusion

In the context of the internet and **Big Data**, RDBMS systems fall short due to their limitations in handling large-scale, unstructured, and distributed data. While RDBMS excels at transactional consistency and structured data storage, it is not designed for the high scalability, flexibility, and performance required by modern internet-driven applications. **NoSQL** databases have emerged as the preferred choice for handling Big Data, providing the ability to manage large volumes of diverse data in real-time, with distributed, high-availability architectures.

### Types of NoSQL Databases

NoSQL databases are designed to handle various types of data and are classified into several categories based on how data is stored and managed. Here’s a breakdown of the main types of NoSQL databases:

---

### 1. **Document Database**

**Document databases** store data in the form of documents, which are structured sets of **key-value pairs** similar to a JSON object. Each document encodes and encapsulates data, and documents are stored and retrieved using unique keys.

- **Structure**:
  - Documents are stored in formats like **JSON**, **BSON**, or **XML**.
  - Each document contains **key-value pairs**, but the structure can vary between documents, offering flexibility.

- **Key Characteristics**:
  - **Encapsulated Data**: Documents represent entire entities, and their data is not split into smaller components like in traditional relational databases. This allows for easy and efficient storage and retrieval.
  - **Unique Keys**: Documents are addressed by a unique key, which makes it easy to retrieve entire documents using this key.
  - **Querying by Keys or Content**: You can retrieve documents based on their unique keys or by querying their contents.

- **Advantages**:
  - Flexible data modeling.
  - Efficient for handling complex and varied data structures.
  - Supports nested data (e.g., arrays, objects within objects).

- **Notable Databases**:
  - **MongoDB**: The most popular document database, known for its scalability and flexibility.
  - **CouchDB**: A document store that uses JSON to store data, JavaScript as its query language, and HTTP for the API.

---

### 2. **Key-Value Store**

A **Key-Value Store** is the simplest type of NoSQL database, storing data as a collection of key-value pairs. Every item in the database is stored as a key (a unique identifier) and its corresponding value (which can be any type of data).

- **Structure**:
  - Data is stored as **key-value pairs**, where the key is unique, and the value can be a string, blob, JSON object, or any other data type.

- **Key Characteristics**:
  - **Efficient Lookup**: Retrieval of values is done by looking up the key. This provides highly efficient reads and writes.
  - **Simple Data Structure**: The simplicity of key-value pairs makes this database model fast and scalable.
  
- **Use Cases**:
  - Caching (e.g., storing frequently accessed data).
  - Session storage for web applications.
  - Storing configuration settings.

- **Notable Databases**:
  - **Redis**: An in-memory key-value store known for its speed and flexibility, used for caching and real-time analytics.
  - **DynamoDB**: Amazon’s scalable, managed key-value store.
  - **Riak**: A distributed key-value store known for its fault tolerance.

---

### 3. **Graph Databases**

**Graph databases** store data in the form of nodes, edges, and properties to represent and traverse relationships between data elements. This makes them well-suited for data that is highly connected and requires frequent querying of relationships.

- **Structure**:
  - **Nodes**: Represent entities (e.g., people, products).
  - **Edges**: Represent relationships between nodes (e.g., friendships, likes).
  - **Properties**: Attributes associated with both nodes and edges.

- **Key Characteristics**:
  - **Efficient Traversal of Relationships**: Graph databases are optimized for querying and analyzing relationships between nodes, making them ideal for highly connected data.
  - **Dynamic Schema**: Like document databases, graph databases offer flexible schema capabilities.
  - **Rich Data Representation**: Complex relationships between data elements are easy to represent.

- **Use Cases**:
  - Social networks (e.g., storing and analyzing relationships between users).
  - Recommendation engines (e.g., suggesting products based on user interactions).
  - Fraud detection (e.g., identifying suspicious patterns by analyzing relationships).

- **Notable Databases**:
  - **Neo4j**: The most popular graph database, known for its high performance and ability to handle complex queries.
  - **ArangoDB**: A multi-model database that includes support for graphs.
  - **Amazon Neptune**: A managed graph database service that supports both property graphs and RDF (Resource Description Framework).

---

### 4. **Column-Family Store (Wide-Column Store)**

**Column-family stores** organize data into rows and columns but, unlike RDBMS, each row can have a different set of columns, making it more flexible and scalable. They are also known as **wide-column stores**.

- **Structure**:
  - Data is stored in **rows** grouped into **column families**. Each row doesn’t need to have the same columns as other rows.
  - Designed to handle **large-scale, distributed datasets**.

- **Key Characteristics**:
  - **Efficient for Read and Write Operations**: Optimized for handling large-scale datasets with high throughput.
  - **Flexible Schema**: Column families can have dynamic columns, making the schema flexible.

- **Use Cases**:
  - Analytical applications with large datasets.
  - Time-series data (e.g., sensor logs, financial data).
  - Event logging.

- **Notable Databases**:
  - **Cassandra**: A highly scalable and fault-tolerant wide-column store designed for handling large amounts of structured data across many commodity servers.
  - **HBase**: A Hadoop-compatible, distributed column-family store used for large-scale, real-time read/write access.

---

### Summary of NoSQL Database Types:

| **Type**              | **Description**                                                                  | **Example Databases**                            |
|-----------------------|----------------------------------------------------------------------------------|-------------------------------------------------|
| **Document Database**  | Stores data as documents in formats like JSON, XML, BSON.                       | MongoDB, CouchDB                                |
| **Key-Value Store**    | Stores data as simple key-value pairs.                                           | Redis, DynamoDB, Riak                           |
| **Graph Database**     | Stores data as nodes and edges representing relationships between entities.      | Neo4j, ArangoDB, Amazon Neptune                 |
| **Column-Family Store**| Stores data in rows and dynamic columns, organized by column families.           | Cassandra, HBase                                |

NoSQL databases are designed to address the limitations of traditional relational databases, offering better scalability, flexibility, and performance for certain types of data and workloads, especially those involving **Big Data** and real-time applications.
### Column-Family Store (Wide-Column Store)

**Column-family stores**, also known as **wide-column stores**, organize data into rows and dynamic columns. Each row can have a different set of columns, allowing for more flexibility compared to traditional relational databases.

- **Structure**:
  - Data is stored in **rows** that are grouped into **column families**.
  - Unlike relational databases, rows can have a variable number of columns, meaning that each row in the same column family can store different fields.
  - Column-family databases are optimized for reading and writing large volumes of data.

- **Use Cases**:
  - They are widely used in analytical applications, time-series data, or for event logging, where **high throughput** is essential.
  - Ideal for **Big Data** applications that require storing massive amounts of structured or semi-structured data in a scalable way.

- **Examples**:
  - **Cassandra**: A widely used, highly scalable column-family store designed for distributed data across multiple servers.
  - **HBase**: A Hadoop-compatible database that supports real-time read/write operations and is often used in data warehousing.

---

### Graph Databases

**Graph databases** store data in the form of **nodes**, **edges**, and **properties**. They are specifically designed to handle relationships between entities and are optimized for traversing these relationships.

- **Structure**:
  - **Nodes**: Represent entities such as people, products, or locations.
  - **Edges**: Represent the relationships between nodes (e.g., friendships, likes, ownership).
  - **Properties**: Attributes attached to both nodes and edges (e.g., a user's age or the strength of a friendship).

- **Use Cases**:
  - Social networks (e.g., representing relationships between users).
  - Fraud detection (e.g., tracing suspicious financial transactions by analyzing connections between entities).
  - Recommendation engines (e.g., suggesting products or services based on a user's connections or preferences).

- **Examples**:
  - **Neo4j**: One of the most widely used graph databases, optimized for complex, highly connected data.
  - **Amazon Neptune**: A fully managed graph database service.

---

### BASE Transaction Model

The **BASE model** (which stands for **Basically Available, Soft State, Eventually Consistent**) is a set of principles used in distributed systems, particularly **NoSQL databases**. It provides an alternative to the strict consistency of the ACID model used in relational databases, focusing instead on availability and scalability at the cost of immediate consistency.

#### Components of BASE:

1. **Basically Available**:
   - The system guarantees **availability** even in the event of partial failures. 
   - This means the system will always try to respond to requests, though the data returned might not always be the most up-to-date or accurate.
   - **Availability** is prioritized over consistency in the short term.

2. **Soft State**:
   - The system allows **state changes** to occur even without direct user interactions.
   - Unlike traditional databases, where the state remains fixed unless updated by an application, NoSQL systems may allow intermediate or inconsistent states.
   - The system continuously reconciles and propagates changes to bring the state closer to consistency over time.

3. **Eventually Consistent**:
   - The system guarantees that **eventual consistency** will be achieved, meaning that at some point in the future, all nodes will reflect the same state.
   - This allows for **stale data** or outdated information to be returned temporarily, but the system will work toward consistency without blocking availability.

---

### Key Features of BASE:

1. **Weak Consistency (Stale Data is Okay)**:
   - Unlike the ACID model, where strong consistency is guaranteed, BASE allows weak or **eventual consistency**. Data may not be immediately up-to-date, but the system guarantees it will eventually reach consistency.

2. **Availability**:
   - The system prioritizes **high availability**, meaning it will always respond to requests, even if some nodes or services are down. This ensures that applications remain functional and users can still interact with the system.

3. **Best Effort**:
   - BASE systems often operate on a **best effort** basis. If there are failures, the system doesn't necessarily guarantee strong data correctness or immediate consistency, but it strives to provide the best possible outcome under the circumstances.

4. **Approximate Answers are Okay**:
   - Since the system is not strictly consistent at all times, it may return **approximate answers** to queries that are still good enough for many use cases. This allows for faster query response times.

5. **Aggressive Optimism**:
   - BASE systems often adopt an **optimistic approach**, assuming that conflicts or data inconsistencies will resolve themselves eventually, rather than preventing them from happening. This aggressive optimism helps improve system performance and scalability.

6. **Simpler and Faster**:
   - The BASE approach results in a **simpler and faster** system, especially for read and write operations. By relaxing consistency guarantees, systems can perform tasks more quickly without needing to enforce strict transactional constraints.

---

### BASE vs ACID:

| **Property**           | **BASE** (NoSQL)                             | **ACID** (RDBMS)                       |
|------------------------|----------------------------------------------|----------------------------------------|
| **Consistency**         | Weak, eventual consistency (data may be stale) | Strong, immediate consistency         |
| **Availability**        | High availability (system responds even in failure) | Availability may be compromised during failures |
| **Scalability**         | Horizontally scalable (distributed nodes)    | Limited horizontal scalability        |
| **State**               | Soft state (state may change over time)      | State remains consistent unless explicitly changed |
| **Speed**               | Optimized for high-speed reads and writes    | Slower due to strong transactional guarantees |

---

### Summary of BASE:

- **BASE** transactions allow for greater flexibility in distributed systems, ensuring that the system remains available and fast, even at the cost of immediate consistency.
- It is ideal for **distributed, high-availability systems**, such as **Big Data** platforms, **social networks**, and **e-commerce systems**, where **speed**, **availability**, and **scalability** are more important than strict consistency.
- **Eventually consistent** systems are suited for applications where occasional stale data is acceptable, but eventual correctness is guaranteed.

By prioritizing availability, speed, and flexibility, the BASE model contrasts with the more rigid ACID principles, making it a better fit for large-scale, distributed systems that handle massive amounts of data in real-time.
## References

---

###### Information
- **Date**: 2024.10.16
- **Time**: 15:19
