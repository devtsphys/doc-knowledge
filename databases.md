# Database Reference: Categories, Systems & Tools

> A universal reference on databases — from the fundamentals to modern architectures.

---

## Table of Contents

1. [Dimension 1: Logical Data Model](#dimension-1-logical-data-model)
   - [Relational (SQL)](#11-relational-sql)
   - [Document-Oriented (NoSQL)](#12-document-oriented-nosql)
   - [Key-Value (NoSQL)](#13-key-value-nosql)
   - [Wide-Column (NoSQL)](#14-wide-column-nosql)
   - [Vector Databases](#15-vector-databases)
   - [Graph Databases](#16-graph-databases)
   - [Time-Series Databases](#17-time-series-databases)
   - [Multi-Model Databases](#18-multi-model-databases)
2. [Dimension 2: Workload & Purpose](#dimension-2-workload--purpose)
   - [OLTP](#21-oltp-online-transaction-processing)
   - [OLAP / Data Warehouses](#22-olap--data-warehouses)
   - [Embedded Databases](#23-embedded-databases)
3. [Dimension 3: System Architecture & Scaling](#dimension-3-system-architecture--scaling)
   - [NewSQL](#31-newsql)
   - [Distributed Databases](#32-distributed-databases)
   - [Federated Databases](#33-federated-databases)
4. [Dimension 4: Storage Medium & Operating Model](#dimension-4-storage-medium--operating-model)
   - [In-Memory (IMDB)](#41-in-memory-imdb)
   - [Disk-Based](#42-disk-based)
   - [Cloud-Native / Serverless](#43-cloud-native--serverless)
5. [Cross-Reference & Decision Guide](#cross-reference--decision-guide)

---

## Dimension 1: Logical Data Model

---

### 1.1 Relational (SQL)

**Core Principle:** Data is stored in tables (relations). Each table has a fixed schema with defined columns and data types. Relationships between tables are expressed via foreign keys and JOINs. The foundation is relational algebra.

**Strengths:**
- Strict ACID guarantees (Atomicity, Consistency, Isolation, Durability)
- Powerful, standardized query language (SQL)
- Referential integrity through constraints
- Decades of proven, optimized usage

**Weaknesses:**
- Horizontal scaling (scale-out) is complex
- Rigid schemas make frequent structural changes difficult
- Impedance mismatch between OOP objects and tabular structures

**When to use?** When structured, relational data is present, consistency is critical (financial transactions, ERP systems, HR systems), and complex joins are needed.

#### Popular Systems

| System | Type | Highlight |
|---|---|---|
| **PostgreSQL** | Open Source RDBMS | Extensibility, JSONB, pgvector, PostGIS |
| **MySQL / MariaDB** | Open Source RDBMS | Widely used, InnoDB Engine, web applications |
| **Microsoft SQL Server** | Commercial | T-SQL, BI integration, Windows ecosystem |
| **Oracle Database** | Commercial | Enterprise features, PL/SQL, highest performance |
| **SQLite** | Embedded | Serverless, single file, ideal for local apps |
| **IBM Db2** | Commercial | Mainframe origins, analytics features |

#### SQL – The Query Language

SQL (Structured Query Language) is the standard for relational databases. The most important sub-languages:

| Sub-language | Commands | Purpose |
|---|---|---|
| **DDL** – Data Definition Language | `CREATE`, `ALTER`, `DROP`, `TRUNCATE` | Define schema |
| **DML** – Data Manipulation Language | `SELECT`, `INSERT`, `UPDATE`, `DELETE` | Read & write data |
| **DCL** – Data Control Language | `GRANT`, `REVOKE` | Control permissions |
| **TCL** – Transaction Control Language | `COMMIT`, `ROLLBACK`, `SAVEPOINT` | Manage transactions |

#### Drivers, ORMs & Tooling

| Category | Tool / Package | Language / Ecosystem |
|---|---|---|
| **ORM** | Hibernate / JPA | Java |
| **ORM** | SQLAlchemy | Python |
| **ORM** | Entity Framework Core | .NET / C# |
| **ORM** | Sequelize, Prisma, TypeORM | Node.js / TypeScript |
| **ORM** | ActiveRecord | Ruby on Rails |
| **Query Builder** | jOOQ | Java |
| **Query Builder** | Knex.js | Node.js |
| **Migration Tool** | Flyway, Liquibase | Java-based, DB-agnostic |
| **Migration Tool** | Alembic | Python |
| **GUI Client** | DBeaver | Multi-DB, Open Source |
| **GUI Client** | TablePlus | macOS / Windows |
| **GUI Client** | pgAdmin | PostgreSQL-specific |
| **GUI Client** | SQL Server Management Studio (SSMS) | SQL Server |
| **CLI** | `psql`, `mysql`, `sqlcmd` | Native CLIs |

---

### 1.2 Document-Oriented (NoSQL)

**Core Principle:** Data is stored as self-describing documents (typically JSON/BSON). A document contains all relevant data for an object — including nested structures and arrays. There is no fixed schema (schema-less or schema-flexible).

**Strengths:**
- Flexible, nested data structures (no impedance mismatch)
- Easy horizontal scaling (sharding)
- Fast iteration with changing requirements
- Natural mapping of OOP objects

**Weaknesses:**
- Weak transactions across multiple documents (improving, e.g. MongoDB from v4.0)
- No native JOIN; data is denormalized
- Consistency model is often "Eventual Consistency"

**When to use?** Content management systems, product catalogs, user profile storage, APIs with variable data structures, rapid prototyping.

#### Popular Systems

| System | Highlight |
|---|---|
| **MongoDB** | De-facto standard, Atlas cloud platform, rich ecosystem |
| **CouchDB / PouchDB** | HTTP-native API, offline-first sync (PouchDB for browsers) |
| **Firestore (Firebase)** | Google, realtime sync, mobile-first |
| **Amazon DocumentDB** | MongoDB-compatible, AWS-managed |
| **Azure Cosmos DB (NoSQL API)** | Multi-model, globally distributed |
| **RavenDB** | .NET ecosystem, ACID transactions |
| **Couchbase** | Combination of document store and key-value cache |

#### Query Languages & Drivers

| Category | Tool / Package | Language |
|---|---|---|
| **Native Driver** | `mongodb` (PyMongo) | Python |
| **Native Driver** | `mongoose` | Node.js (ODM with schema validation) |
| **Native Driver** | MongoDB Java Driver | Java |
| **Query Language** | MQL (MongoDB Query Language) | JSON-based |
| **Aggregation** | MongoDB Aggregation Pipeline | JSON-based |
| **GUI Client** | MongoDB Compass | Official MongoDB client |
| **GUI Client** | Robo 3T / Studio 3T | Community tool |

---

### 1.3 Key-Value (NoSQL)

**Core Principle:** The simplest NoSQL structure. A unique key maps to an arbitrary value (string, JSON, binary data). No schema, no query language for value contents; access is exclusively via the key.

**Strengths:**
- Extremely low latency (often < 1 ms)
- Massive throughput for simple operations (GET/SET)
- Trivially scalable horizontally

**Weaknesses:**
- No querying of value contents
- Not suitable for complex data structures or relational queries

**When to use?** Session management, caching layer, real-time leaderboards, feature flags, shopping carts, rate limiting.

#### Popular Systems

| System | Highlight |
|---|---|
| **Redis** | In-memory, data structures (Lists, Sets, Hashes), Pub/Sub, Streams |
| **Memcached** | Simple caching, multi-threaded, no persistence |
| **Amazon DynamoDB** | Serverless, auto-scaling, global tables |
| **Azure Cache for Redis** | Managed Redis on Azure |
| **Etcd** | Distributed key-value store for Kubernetes configuration |
| **Consul (KV)** | Service discovery + key-value store |

#### Drivers & Tooling

| Category | Tool / Package | Language |
|---|---|---|
| **Client** | `redis-py` | Python |
| **Client** | `ioredis`, `node-redis` | Node.js |
| **Client** | Lettuce, Jedis | Java |
| **Client** | StackExchange.Redis | .NET / C# |
| **ORM-like** | Spring Data Redis | Java / Spring |
| **GUI Client** | RedisInsight | Official Redis Ltd. client |
| **CLI** | `redis-cli` | Native CLI |

---

### 1.4 Wide-Column (NoSQL)

**Core Principle:** Data is stored in tables with rows and columns, but unlike SQL the columns are dynamic — each row can have different columns. Data is grouped into column families. Optimized for massively distributed read/write workloads.

**Strengths:**
- Linear scaling to petabyte scale
- High write throughput for distributed workloads
- Excellent read performance with a known row key

**Weaknesses:**
- No flexible querying (no ad-hoc JOIN, no WHERE on arbitrary columns without a secondary index)
- Data modeling must be query-driven
- Complex operations for self-hosted systems

**When to use?** IoT telemetry, clickstream analysis, audit logs, social networks (follower feeds), time-series data at large scale.

#### Popular Systems

| System | Highlight |
|---|---|
| **Apache Cassandra** | Leaderless, masterless, CQL query language, ring topology |
| **ScyllaDB** | Cassandra-compatible, written in C++, significantly higher performance |
| **Apache HBase** | Hadoop ecosystem, HDFS-based, strong consistency |
| **Google Bigtable** | Origin of the wide-column paradigm, basis for Cassandra's design |
| **Azure Table Storage** | Simple, cost-effective, no CQL |
| **Amazon Keyspaces** | Managed Cassandra-compatible on AWS |

#### Query Languages & Drivers

| Category | Tool / Package | Language |
|---|---|---|
| **Query Language** | CQL (Cassandra Query Language) | SQL-like |
| **Driver** | `cassandra-driver` | Python |
| **Driver** | DataStax Java Driver | Java |
| **Driver** | gocql | Go |
| **ORM-like** | Spring Data Cassandra | Java / Spring |
| **GUI Client** | DataStax DevCenter, DBeaver | Multi-platform |

---

### 1.5 Vector Databases

**Core Principle:** Specialized in storing and searching high-dimensional vectors (embeddings). Instead of exact matches, the nearest neighbor (ANN – Approximate Nearest Neighbor) in vector space is found. The backbone of AI/ML applications.

**Strengths:**
- Semantic similarity search (meaning rather than keyword matching)
- Fundamental for RAG (Retrieval Augmented Generation) with LLMs
- Supports image, text, and audio embeddings

**Weaknesses:**
- Results are approximate, not exact
- High memory requirements for large embedding models
- Less suitable for transactional workloads

**When to use?** Semantic search, chatbots with contextual memory (RAG), recommendation systems, duplicate detection, image similarity search.

#### Popular Systems

| System | Highlight |
|---|---|
| **Pinecone** | Fully managed, cloud-native, simple API |
| **Milvus** | Open source, high-performance, scalable |
| **Weaviate** | Open source, GraphQL API, built-in embedding models |
| **Qdrant** | Open source, written in Rust, filterable |
| **Chroma** | Open source, simple, ideal for local development & prototyping |
| **pgvector** | PostgreSQL extension – vector search in existing SQL DBs |
| **Redis Vector Search** | Redis module for vector ANN search |
| **Azure AI Search** | Managed, hybrid search (vector + keyword) |
| **Elasticsearch / OpenSearch** | k-NN search as a feature |

#### Key Concepts & Tools

| Concept / Tool | Description |
|---|---|
| **Embeddings** | Numerical vector representation of text/images via ML model |
| **HNSW** | Hierarchical Navigable Small World – common ANN index algorithm |
| **IVF-Flat** | Inverted File Index – another ANN algorithm |
| **LangChain** | Framework for LLM applications with vector store integration |
| **LlamaIndex** | RAG framework with vector DB connectors |
| **OpenAI Embeddings API** | `text-embedding-ada-002`, `text-embedding-3-*` |
| **Sentence Transformers** | Python library for local embeddings (HuggingFace) |

---

### 1.6 Graph Databases

**Core Principle:** Data is stored as nodes and edges (relationships). Relationships are first-class citizens equal to the data itself and are traversed directly — without costly JOINs. The data model directly corresponds to a graph.

**Strengths:**
- Highly efficient traversal of complex relationship networks
- Natural representation of interconnected data
- Flexible schema (property graph)

**Weaknesses:**
- Not the optimal model for tabular bulk data
- Less widespread, smaller community than SQL/document
- OLAP analytics across the entire graph can be expensive

**When to use?** Social networks (follower graphs), fraud detection (network analysis), knowledge graphs, recommendation systems, routing & network topologies, identity and access management.

#### Popular Systems

| System | Highlight |
|---|---|
| **Neo4j** | De-facto standard, property graph, Cypher query language |
| **Amazon Neptune** | Managed, supports property graph (Gremlin) & RDF (SPARQL) |
| **Azure Cosmos DB (Gremlin API)** | Graph API on Cosmos DB |
| **ArangoDB** | Multi-model: graph + document + key-value |
| **TigerGraph** | High-performance for analytical graph workloads |
| **JanusGraph** | Open source, scalable, HBase/Cassandra as backend |

#### Query Languages

| Language | System | Paradigm |
|---|---|---|
| **Cypher** | Neo4j, compatible systems | Declarative, ASCII-art patterns |
| **Gremlin** | Apache TinkerPop, Amazon Neptune | Imperative, traversal-based |
| **SPARQL** | RDF stores (Semantic Web) | Standard for linked data |
| **GQL** | ISO standard (from 2024) | Upcoming graph SQL standard |

#### Drivers & Tooling

| Tool / Package | Language |
|---|---|
| `neo4j` (official driver) | Python, Java, .NET, JavaScript, Go |
| `py2neo` | Python (higher abstraction level) |
| Spring Data Neo4j | Java / Spring |
| Neo4j Desktop / Browser | GUI client & query workbench |

---

### 1.7 Time-Series Databases

**Core Principle:** Optimized for timestamped data points arriving at regular or irregular time intervals. Time is the primary index. Provides special functions for downsampling, aggregation over time windows, and automatic data retention management.

**Strengths:**
- Extremely high ingest rates for metrics and events
- Built-in time functions (rolling averages, resampling)
- Efficient compression of temporal data patterns
- Automatic deletion of old data (retention policies)

**Weaknesses:**
- Not suitable for relational or document-based data
- Updates and deletes of individual data points rarely supported

**When to use?** DevOps monitoring (CPU, RAM, network), IoT sensor telemetry, financial market data, Application Performance Monitoring (APM), energy consumption measurement.

#### Popular Systems

| System | Highlight |
|---|---|
| **InfluxDB** | Open source, Flux language, Telegraf agent, Kapacitor alerting |
| **TimescaleDB** | PostgreSQL extension – time-series + full SQL |
| **Prometheus** | Pull-based, PromQL, de-facto standard for K8s monitoring |
| **VictoriaMetrics** | High-performance Prometheus-compatible alternative |
| **OpenTSDB** | HBase-based, scalable monitoring |
| **QuestDB** | High-performance, SQL-compatible |
| **Amazon Timestream** | Serverless, AWS-managed |
| **Azure Data Explorer** | Analytics-focused, KQL (Kusto Query Language) |
| **Graphite** | Older, widely used, basis of many legacy stacks |

#### Query Languages & Tooling

| Category | Tool | Description |
|---|---|---|
| **Query Language** | PromQL | Prometheus – expressions for metrics |
| **Query Language** | Flux | InfluxDB v2 – functional language |
| **Query Language** | KQL | Azure Data Explorer / Kusto |
| **Query Language** | SQL (TimescaleDB) | Standard SQL with time extensions |
| **Visualization** | Grafana | De-facto visualization layer for all time-series DBs |
| **Collection Agent** | Telegraf | InfluxDB ecosystem |
| **Collection Agent** | Prometheus Exporters | For virtually any metric source |

---

### 1.8 Multi-Model Databases

**Core Principle:** A single database engine natively supports multiple data models (e.g. document, graph, key-value, wide-column) via dedicated APIs. No data migration overhead between systems.

**Strengths:**
- Operational overhead reduced by fewer systems
- Consistent global data distribution across all models
- Flexibility: the right model for each use case within one project

**Weaknesses:**
- No single model reaches the depth of a specialized system
- Higher operational complexity
- Vendor lock-in can be more significant

**When to use?** Global applications with multiple data needs requiring low latency worldwide; when minimizing operational complexity is a priority.

#### Popular Systems

| System | Supported Models | Highlight |
|---|---|---|
| **Azure Cosmos DB** | Document, Key-Value, Graph (Gremlin), Wide-Column (Cassandra API), Table | Global distribution, 5 consistency levels, SLA-guaranteed latency |
| **ArangoDB** | Document, Graph, Key-Value | Open source, AQL (ArangoDB Query Language) |
| **OrientDB** | Document, Graph, Key-Value, Object | Java-based, SQL-like syntax |
| **Couchbase** | Document, Key-Value, Analytics | N1QL (SQL for JSON), mobile sync |
| **FaunaDB** | Document, Relational, Graph | Serverless, global consistency via Calvin protocol |

---

## Dimension 2: Workload & Purpose

---

### 2.1 OLTP (Online Transaction Processing)

**Core Principle:** Optimized for a very high volume of short, concurrent transactions. Each operation (e.g. purchase, login, booking) is a small, atomic unit. High read/write throughput at the individual record level.

**Characteristics:**
- Many concurrent users
- Short transactions (millisecond range)
- Strict ACID guarantees
- Normalized data model (to avoid redundancy)
- Row-oriented storage

**When to use?** E-commerce (checkout), online banking, booking systems, ERP systems, CRM systems, ticketing.

#### Typical OLTP Systems

| System | Type | Note |
|---|---|---|
| **PostgreSQL** | Open Source SQL | Gold standard, excellent ACID guarantees |
| **MySQL / MariaDB** | Open Source SQL | LAMP stack, web applications |
| **SQL Server** | Commercial | Enterprise, .NET integration |
| **Oracle Database** | Commercial | Mission-critical enterprise workloads |
| **Amazon Aurora** | Cloud-native SQL | MySQL/PostgreSQL-compatible, 5x performance |
| **Google Cloud Spanner** | NewSQL | OLTP with global scaling |
| **MongoDB** | NoSQL Document | OLTP for non-relational data |

#### Key OLTP Concepts

| Concept | Explanation |
|---|---|
| **ACID** | Atomicity, Consistency, Isolation, Durability |
| **Locking / MVCC** | Mechanisms for isolating concurrent transactions |
| **Connection Pooling** | `PgBouncer`, `HikariCP` – managing DB connections |
| **Sharding** | Horizontal partitioning for scale-out |
| **Read Replicas** | Write load on primary, read operations distributed to replicas |

---

### 2.2 OLAP / Data Warehouses

**Core Principle:** Optimized for complex, analytical queries over very large volumes of historical data. Written infrequently, read often. Columnar storage enables extremely fast aggregations across individual columns.

**Characteristics:**
- Few concurrent but complex queries (minutes rather than milliseconds)
- Denormalized data model (star schema, snowflake schema)
- Column-oriented storage (column store)
- Massively parallel processing (MPP)

**When to use?** Business Intelligence (BI), reporting, dashboards, financial analysis, customer behavior analysis, historical data evaluation.

#### Data Warehouse Systems

| System | Type | Highlight |
|---|---|---|
| **Snowflake** | Cloud-native | Separation of storage and compute, multi-cloud |
| **Google BigQuery** | Cloud-native (GCP) | Serverless, pay-per-query |
| **Amazon Redshift** | Cloud-native (AWS) | Columnar, MPP, S3 integration |
| **Azure Synapse Analytics** | Cloud-native (Azure) | SQL pools + Spark integration |
| **ClickHouse** | Open Source | Extremely fast, real-time analytics |
| **DuckDB** | Embedded OLAP | In-process, ideal for local analytics |
| **Apache Druid** | Real-Time OLAP | Sub-second queries on event data |
| **Databricks (Lakehouse)** | Cloud | Delta Lake, Unity Catalog, Spark |

#### ELT/ETL Tools for Data Warehouses

| Tool | Type | Description |
|---|---|---|
| **dbt (data build tool)** | Transformation | SQL-based transformations with versioning |
| **Apache Airflow** | Orchestration | DAG-based workflow management |
| **Fivetran / Airbyte** | Data Integration | Managed / open-source ELT connectors |
| **Apache Spark** | Processing | Distributed data processing |
| **Great Expectations** | Data Quality | Testing framework for data pipelines |
| **Apache Kafka** | Streaming Ingest | Stream real-time data into a DWH |

---

### 2.3 Embedded Databases

**Core Principle:** The database runs as a library directly inside the application process — no separate database server, no network connection. Data is typically stored in a single file.

**Strengths:**
- Zero administration
- No network latency (in-process)
- Simple distribution (one file)
- Ideal for offline-first applications

**Weaknesses:**
- No multi-client support over the network
- Limited scalability

**When to use?** Mobile apps (iOS/Android), desktop applications, browser-based apps, testing & CI/CD, local prototypes, IoT devices.

#### Popular Systems

| System | Language / Platform | Highlight |
|---|---|---|
| **SQLite** | Universal | World's most widely used database, stable SQL |
| **H2 Database** | Java | In-memory or file-based, ideal for Java testing |
| **HSQLDB** | Java | Similar to H2, common in older Java projects |
| **DuckDB** | Universal | OLAP-embedded, Python/R integration |
| **LevelDB / RocksDB** | C++ (embedded in many systems) | Key-value, developed by Google / Meta |
| **Realm** | Mobile (iOS/Android) | Object-oriented, offline-first, sync |
| **PouchDB** | JavaScript/Browser | CouchDB-compatible, browser persistence |
| **LMDB** | C | Lightning Memory-Mapped Database, very fast |

---

## Dimension 3: System Architecture & Scaling

---

### 3.1 NewSQL

**Core Principle:** The "third wave" — combines the ACID guarantees and SQL power of traditional relational databases with the horizontal scalability of NoSQL systems. Enables global, distributed transactions.

**Strengths:**
- Full ACID transactions across distributed nodes
- Standards-compliant SQL
- Automatic sharding and rebalancing
- Linear scalability

**Weaknesses:**
- Higher latency than classic RDBMS (network overhead for consensus)
- Complex infrastructure
- Higher cost

**When to use?** Global transaction systems that simultaneously require high consistency and massive scale (global financial platforms, global inventory systems).

#### Popular Systems

| System | Highlight |
|---|---|
| **Google Cloud Spanner** | Atomic clocks for global consistency (TrueTime API) |
| **CockroachDB** | Open-core, PostgreSQL-compatible, geo-partitioning |
| **YugabyteDB** | PostgreSQL-compatible, open source, Cassandra API |
| **TiDB** | Open source, MySQL-compatible, HTAP (OLTP + OLAP) |
| **NuoDB** | Cloud-based, patented Durable Atom concept |
| **VoltDB** | In-memory NewSQL, real-time analytics |

---

### 3.2 Distributed Databases

**Core Principle:** Data is physically distributed across multiple nodes but behaves logically as a single system. Fault tolerance and scaling through replication and sharding.

**The CAP Theorem** (fundamental for distributed systems):

| Property | Description |
|---|---|
| **C**onsistency | All nodes see the same data at the same time |
| **A**vailability | Every request receives a response (not necessarily up-to-date) |
| **P**artition Tolerance | The system works despite network failures |

> A distributed system can only guarantee 2 of the 3 properties simultaneously.

#### Replication Strategies

| Strategy | Description | Systems |
|---|---|---|
| **Leader-Follower** | One master writes, replicas read | MySQL Replication, PostgreSQL Streaming Replication |
| **Multi-Master** | Multiple nodes accept writes | Galera Cluster, CockroachDB |
| **Leaderless (Quorum)** | No dedicated master, majority vote | Cassandra, DynamoDB |
| **Raft Consensus** | Formal leader election algorithm | etcd, CockroachDB, TiDB |
| **Paxos** | Older consensus algorithm | Google Chubby, Zookeeper |

#### Sharding Strategies

| Strategy | Description |
|---|---|
| **Range-based Sharding** | Data split by key value range |
| **Hash-based Sharding** | Key is hashed, hash determines the shard |
| **Directory-based Sharding** | A lookup table maps keys to shards |
| **Geo-based Sharding** | Data partitioned by region |

---

### 3.3 Federated Databases

**Core Principle:** A virtual query layer that makes multiple heterogeneous, independent data sources (SQL, NoSQL, APIs, files) appear as a single logical database — without physically integrating the data.

**Strengths:**
- No complex ETL/ELT; data stays at the source
- Access to diverse systems via a unified query language
- Ideal for legacy integration

**Weaknesses:**
- Performance depends on the source systems
- Complex optimization of distributed queries
- Consistency guarantees are difficult

**When to use?** Enterprise integration of heterogeneous legacy systems, data virtualization, ad-hoc cross-system analysis without data migration.

#### Popular Systems & Tools

| Tool / System | Description |
|---|---|
| **Apache Arrow Flight SQL** | High-performance protocol for data queries over a network |
| **Trino (formerly PrestoSQL)** | Distributed SQL query engine over Hive, S3, Kafka, RDBMS |
| **AWS Athena** | Serverless SQL on S3 data (Presto-based) |
| **Dremio** | Data lakehouse engine, Apache Arrow-based |
| **Denodo** | Commercial data virtualization platform |
| **IBM Data Virtualization** | Enterprise solution for data federation |

---

## Dimension 4: Storage Medium & Operating Model

---

### 4.1 In-Memory (IMDB)

**Core Principle:** The primary data store is RAM instead of disk/SSD. Since RAM access is ~100,000x faster than disk I/O, dramatically lower latency is achieved. Persistence is optionally secured on disk via snapshots (RDB) or logs (AOF/WAL).

**Strengths:**
- Sub-millisecond latency
- Enormous read/write throughput
- Ideal as a caching layer

**Weaknesses:**
- Expensive (RAM costs more than SSD)
- Risk of data loss on system failure (depending on persistence config)
- Limited by available RAM

**When to use?** Session caching, database query caching, real-time leaderboards, Pub/Sub messaging, gaming states.

#### Popular Systems

| System | Highlight |
|---|---|
| **Redis** | Data structures, Pub/Sub, Streams, Lua scripting, cluster mode |
| **Memcached** | Simple, high-performance caching; no persistence |
| **Apache Ignite** | In-memory data grid + distributed computing |
| **Hazelcast** | Distributed in-memory data grid, Java-centric |
| **SAP HANA** | Enterprise in-memory column store for ERP/analytics |
| **VoltDB** | ACID transactions in RAM, NewSQL |
| **Aerospike** | Hybrid (RAM + Flash SSD), very high throughput |

#### Redis Persistence Concepts

| Mechanism | Description |
|---|---|
| **RDB (Snapshot)** | Periodic point-in-time snapshots to disk |
| **AOF (Append-Only File)** | Every write operation is logged |
| **RDB + AOF** | Combination for maximum data safety |
| **No Persistence** | Pure caching – data loss on restart is accepted |

---

### 4.2 Disk-Based

**Core Principle:** The traditional standard. Data is persistently stored on HDD or SSD. Modern systems use sophisticated caching strategies (buffer pool, page cache) to keep frequently accessed data in RAM.

**Key Technologies:**

| Concept | Description |
|---|---|
| **B-Tree / B+-Tree** | Standard index structure for read-heavy workloads (PostgreSQL, MySQL) |
| **LSM-Tree** | Log-Structured Merge-Tree – optimized for write-heavy workloads (Cassandra, RocksDB) |
| **WAL (Write-Ahead Log)** | Crash safety by logging before the actual write |
| **Buffer Pool** | In-memory cache for frequently used disk pages (InnoDB Buffer Pool) |
| **VACUUM / Autovacuum** | PostgreSQL mechanism for cleaning up dead tuples (MVCC) |

#### Storage Engines

| Engine | Database | Characteristics |
|---|---|---|
| **InnoDB** | MySQL / MariaDB | ACID, row-level locking, MVCC (default) |
| **MyISAM** | MySQL | Legacy, table-level locking, no ACID |
| **WiredTiger** | MongoDB | Default engine since MongoDB 3.2, compression |
| **RocksDB** | MyRocks (MySQL), TiKV | LSM-Tree, write-optimized |
| **Heap Files / Slotted Pages** | PostgreSQL | Standard storage layout |

---

### 4.3 Cloud-Native / Serverless

**Core Principle:** No server management. Storage and compute scale dynamically and independently. Billing based on actual usage (pay-per-request or pay-per-second). High availability and replication are inherent.

**Strengths:**
- No capacity planning required
- Automatic scaling to zero (free when idle)
- Highest availability through provider infrastructure
- No patching, no OS management

**Weaknesses:**
- Vendor lock-in
- Cold starts / throttling during unexpected traffic spikes
- Cost structure can be more expensive than dedicated instances at high, constant traffic

**When to use?** Startups, unpredictable traffic, microservices, event-driven architectures, development and test environments.

#### Popular Cloud-Native Databases

| System | Cloud | Type |
|---|---|---|
| **Amazon DynamoDB** | AWS | Key-value / document, serverless-first |
| **Amazon Aurora Serverless** | AWS | MySQL/PostgreSQL-compatible, auto-pause |
| **Google Cloud Firestore** | GCP | Document-based, realtime sync |
| **Google Cloud Spanner** | GCP | Global NewSQL, serverless option |
| **Azure Cosmos DB Serverless** | Azure | Multi-model, per-request billing |
| **Azure SQL Database Serverless** | Azure | SQL, auto-pause and auto-resume |
| **Snowflake** | Multi-Cloud | DWH, automatic compute scaling |
| **PlanetScale** | Multi-Cloud | MySQL-compatible, branching workflow |
| **Neon** | Multi-Cloud | PostgreSQL, serverless, branching |
| **Turso** | Multi-Cloud | SQLite at the edge (libSQL) |
| **Supabase** | Multi-Cloud | PostgreSQL with BaaS features |

---

## Cross-Reference & Decision Guide

### Decision Matrix: Which Database for Which Use Case?

| Use Case | Recommended Category | Example Systems |
|---|---|---|
| E-Commerce Checkout | OLTP / Relational | PostgreSQL, MySQL, Aurora |
| User Sessions / Auth Tokens | Key-Value In-Memory | Redis, Memcached |
| Product Catalog (variable structure) | Document-Oriented | MongoDB, Firestore |
| Social Network (follows) | Graph | Neo4j, Amazon Neptune |
| Business Intelligence Reports | OLAP / Data Warehouse | Snowflake, BigQuery, Redshift |
| IoT Sensor Data | Time-Series | InfluxDB, TimescaleDB, Prometheus |
| AI Chatbot with Context (RAG) | Vector | Pinecone, Weaviate, pgvector |
| Global Transactions | NewSQL | Google Spanner, CockroachDB |
| Mobile Offline App | Embedded | SQLite, Realm |
| Legacy System Integration | Federated | Trino, Dremio |
| Massive IoT Write Workload | Wide-Column | Cassandra, ScyllaDB |
| Startup / Unpredictable Traffic | Serverless | DynamoDB, Cosmos DB Serverless |

### Consistency Model Comparison

| Model | Description | Systems |
|---|---|---|
| **Strong Consistency** | Always read the most recent write | SQL systems, Spanner, etcd |
| **Eventual Consistency** | All nodes converge eventually | Cassandra, DynamoDB (default), CouchDB |
| **Causal Consistency** | Causally dependent writes are visible to each other | MongoDB (sessions), Cosmos DB |
| **Session Consistency** | Everything is consistent within a session | Azure Cosmos DB (session level) |
| **Bounded Staleness** | Reads can be at most X seconds stale | Azure Cosmos DB |

### Comparison: SQL vs. NoSQL

| Criterion | SQL (Relational) | NoSQL |
|---|---|---|
| **Schema** | Fixed, defined upfront | Flexible, at runtime |
| **Scaling** | Vertical (scale-up) primarily | Horizontal (scale-out) |
| **Consistency** | ACID | Eventual Consistency (often) |
| **Querying** | Declarative (SQL) | API-specific |
| **Joins** | Native | Denormalization or application-side |
| **Maturity** | 50+ years | 15–20 years |
| **Core Strength** | Complex queries, data integrity | Scalability, flexibility, speed |
