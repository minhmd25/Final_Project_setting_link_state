# 🔄 Link-State Routing Algorithm

This project explains the **Link-State (LS)** dynamic routing algorithm used in computer networks to compute the **shortest path** from a router to all other destinations.

## 📌 Overview

The **Link-State algorithm** enables each router in a network to build a complete map of the network topology. It then uses **Dijkstra’s algorithm** to compute the shortest path to all other nodes. This ensures efficient, loop-free routing.

---

## 🚀 Key Steps of the Link-State Algorithm

### 1. 🧩 Link Information Collection

Each router:

- Identifies its **direct neighbors**.
- Measures the **cost** of each direct link.
- Creates a **Link State Advertisement (LSA)** containing:
  - A list of neighbors
  - The link cost to each

### 2. 🌐 Dissemination via Flooding

- Routers **flood** their LSA across the entire network.
- All routers receive LSAs from every other router.
- LSAs are tagged with a **sequence number** to ensure only the most recent version is processed.

### 3. 🗂️ Building the Link State Database (LSDB)

Each router:

- Stores all received LSAs into a **Link State Database (LSDB)**.
- Constructs a **weighted graph** representing the full network topology.

### 4. 🧮 Shortest Path Calculation (Dijkstra’s Algorithm)

Each router:

- Runs **Dijkstra’s algorithm** on its LSDB.
- Computes the shortest path to all destinations.
- Builds a **Forwarding Table** mapping:
  - Each destination ➜ to the **next-hop** router.

### 5. 🔄 Dynamic Updates

When the network changes (e.g. a link is added or removed):

- Affected routers:
  - Generate updated LSAs (with incremented sequence numbers).
  - Flood the new LSAs across the network.
- All routers:
  - Update their LSDBs.
  - Re-run Dijkstra’s algorithm.
  - Refresh their forwarding tables.

---

## 📚 Technologies / Concepts Involved

- Graph Theory
- Dijkstra’s Algorithm
- Flooding Mechanism
- Network Routing
- Dynamic Link-State Protocols (e.g., OSPF)

---

## 🧠 Author Notes

This project illustrates the foundation of modern link-state routing protocols such as **OSPF (Open Shortest Path First)**.  
By understanding LSAs and Dijkstra’s algorithm, you can grasp how modern routers make fast, intelligent routing decisions.
