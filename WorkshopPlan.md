# Workshop Plan: Introduction to Databases and ArangoDB

## 1. Introduction & Icebreaker

* Introduce yourselves and participants.
* Ask participants about their preferred databases, why they choose them, and what they use them for.
* Discuss differences between databases and database management systems (DBMS).

  * **Database:** The physical storage of data.
  * **DBMS:** The software that manages, queries, and maintains the database.

## 2. Overview of Database Types

### 2.1 Flat File Database

* Earliest form of data storage, stored in a single table.
* Easy to implement, but locating data becomes difficult as it grows.
* Highlights the need for more functional DBMS.

### 2.2 Hierarchical Database

* Treelike structure: one parent record can have multiple child records.
* Example: IBM's Information Management System.

### 2.3 Network Database

* Hierarchical model but child records can link to multiple parents.
* Also called a graph model.
* Example: Integrated Data Store.

### 2.4 Object-Oriented Database

* Stores data as objects (including methods, names, addresses).
* Example: Berkeley DB software library.

### 2.5 Relational Database

* Most common type.
* Data stored in tables (rows = records, columns = attributes).
* Each record has a unique identity.
* Relationships created using primary keys.
* Examples: MySQL, PostgreSQL.

### 2.6 NoSQL Database

* Flexible, schema-less storage, often used for large-scale distributed data.
* Types: Document stores, key-value stores, columnar, graph databases.

### 2.7 Cloud-Based Database

* Hosted on cloud platforms.
* Provides scalability, reliability, and managed services.

## 3. Graph Databases

* **Definition:** Networks of nodes and edges.

  * Nodes (vertices) = entities (person, book, sensor).
  * Edges = relationships between nodes.
* **Use cases:** Recommendation engines, fraud detection, knowledge graphs.
* **Problem solved:** Provides an expressive model that aligns with human cognitive patterns, allowing semantic queries and analytics on connected data.

## 4. Introduction to ArangoDB

### 4.1 Key Facts

* Initial release: 2011.
* Written in C++.
* Based in Germany.
* Open-source with enterprise options.
* Multi-model database: graph, document, key-value.
* Can use RocksDB as a storage engine.
* Offers web interface, containerized deployment, and JSON-based storage.
* Flexible schema: collections can be schema-less by default.

### 4.2 Why ArangoDB Exists

* Scalable graph database for connected data.
* Combines analytical power of graphs with search engine, JSON support, vector indexes.
* Unified query language (AQL) allows querying across multiple data models in a single request.
* Reduces total cost of ownership by combining multiple data models into one engine.

### 4.3 Use Cases & Relevance

* Flexible data access patterns for complex applications.
* Supports hybrid workloads: documents, key-value, moderate-depth graph traversals.
* Still relevant due to query flexibility, multi-model support, and developer productivity.

### 4.4 Community Insights

* Positive: JSON storage over HTTP, unified query language, avoiding custom API development.
* Negative: Write-write conflicts under heavy load, engine crashes reported by some users.

## 5. Competitors & Comparison

### 5.1 Neo4j

* Native property graph database.
* Optimized for highly connected data and deep graph analytics.
* Strong ACID transactions and enterprise governance.
* Advanced Graph Data Science (GDS) capabilities.

### 5.2 ArangoDB vs Neo4j

| Feature        | ArangoDB                                       | Neo4j                                                 |
| -------------- | ---------------------------------------------- | ----------------------------------------------------- |
| Data Model     | Multi-model (documents, key-value, graphs)     | Native graph                                          |
| Query Language | AQL (unified)                                  | Cypher (graph-focused)                                |
| Performance    | Hybrid workloads, cross-shard traversal slower | Fast multi-hop traversals                             |
| Scalability    | Horizontal scaling, SmartGraphs                | Causal clustering, Fabric federation                  |
| Analytics      | Basic + Pregel                                 | Full GDS suite                                        |
| Operations     | Simplified for multi-model                     | Strong governance for large graph-centric enterprises |

### 5.3 Choosing the Right DB

* **ArangoDB:** Use when graph is one component of a multi-model application; hybrid workflows; simpler operations.
* **Neo4j:** Use when relationships are central; deep or complex graph traversals; advanced graph analytics; enterprise governance.

## 6. Workshop Setup

* Using containers for easy deployment and reset.
* Pull latest ArangoDB version using `latest` tag.
* Hands-on: storing JSON-based data, creating collections, adding edges to build a graph, running queries.

## 7. Research & Presentation Focus

* **Topics to cover:**

  * Why ArangoDB exists and problem solved.
  * Relevance and modern use cases.
  * Competitor comparison.
  * Advantages and drawbacks.
  * Practical setup and usage (containers, collections, queries).
* **References:** Use high-quality sources and provide links.
* **Complexity:** Include both conceptual understanding and hands-on demonstration.

---

This plan organizes the workshop from general database concepts to ArangoDB specifics, including context, comparisons, and practical exercises.
