
## 1. Introduction to Arango DB

- **What is Arango DB?**
    
    - A **multi-model database**: supports document, graph, and key/value models in one system.
        
    - Query language: **AQL (Arango Query Language)**.
        
    - Used in recommendation engines, fraud detection, IoT, knowledge graphs, and more.
        
- **Key Features:**
    
    - Runs natively in a **Docker container**.
        
    - Comes with a **web interface** at [http://localhost:8529](http://localhost:8529/).
        
    - Flexible data modeling: combine documents and graphs in the same query.
        

---

## 2. Competitors & Differences

**Closest competitors:**

- **MongoDB** (document-oriented only)
    
- **Neo4j** (graph database only)
    
- **Cassandra** (wide-column store)
    
- **PostgreSQL** (relational with some JSON support)
    

**Big Difference:**

- Arango DB uniquely combines **multiple data models natively**. You don’t need separate databases for documents, graphs, and search.
    

---

## 3. Setup & Environment (Target: ≤ 30 min on any OS)

- **Install with Docker:**
    
    ```bash
    docker run -e ARANGO_ROOT_PASSWORD=root -p 8529:8529 arangodb
    ```
    
- Access Web UI → [http://localhost:8529](http://localhost:8529/)
    
- Log in with username: `root`, password: `root` (or your choice).
    

**Checklist / Possible Issues:**

- Docker not installed → Provide instructions for Windows/Mac/Linux.
    
- Port conflicts on `8529` → Show how to change exposed port.
    
- Network/firewall issues → Use Docker Desktop network settings.
    

---

## 4. Workshop Format

-  **Keep it interactive** → no long lectures in a row.
    
-  Encourage participants to:
    
    - Run commands themselves.
        
    - Share issues/errors.
        
    - Work in pairs for troubleshooting.
        
-  Goal: everyone has a running DB and first queries within 30 minutes.
    

---

## 5. Exercises (Different Tiers)

### Tier 1: Basics (Warm-up)

- Create a **database** and a **collection**.
    
- Insert a few documents.
    
- Run a simple query.
    

### Tier 2: AQL Queries

- Filter documents by field.
    
- Sort results.
    
- Aggregate (e.g., count users > 30).
    

### Tier 3: Graphs

- Create a graph with vertex + edge collections.
    
- Insert cities and flights.
    
- Query connections (1 or 2 hops).
    

### Tier 4: Challenge (Optional)

- Build a **social network graph**.
    
- Query: find "friends-of-friends" of a user.
    
- Bonus: find shortest path between two users.
    

---

## 6. Wrap-Up

- Recap of key concepts: multi-model, AQL, graphs.
    
- Discuss real-world use cases.
    
- Share resources:
    
    - [ArangoDB Docs](https://www.arangodb.com/docs/)
        
    - [AQL Tutorial](https://www.arangodb.com/learn/aql/)
        
    - [ArangoGraph Cloud](https://cloud.arangodb.com/)
        

---

 By the end, participants should:

1. Know what ArangoDB is and how it compares to others.
    
2. Be comfortable running it locally in Docker.
    
3. Have hands-on experience with collections, queries, and graphs.
    
4. Be inspired to explore further projects.
