# 🚀 pgr_johnson() – All-Pairs Shortest Path for pgRouting (GSoC 2025)

> _Development repository for Johnson's Algorithm integration into pgRouting using Boost Graph Library_

---

## 🌐 Overview

This repo contains prototype modules and test utilities for the `pgr_johnson()` function — a native All-Pairs Shortest Path solution for **sparse, negative-weight geospatial graphs** inside pgRouting.

**Status:** 🧪 Early-stage prototype (pre-GSoC selection)  
**Author:** [Alay Sharma](https://github.com/mrvenom17)  
**Mentoring Org:** OSGeo / pgRouting

---

## 📦 Planned Features

- Boost::Graph based implementation of Johnson’s Algorithm
- Seamless integration with pgRouting's internal graph loaders
- SQL-callable wrapper following `pgr_dijkstra` conventions
- Bellman-Ford preprocessing with negative cycle detection
- Dijkstra pass for all nodes with reweighted edges
- Unit + Regression + Performance test suite

---

## 🔧 Structure

```bash
include/            # Function headers
src/                # Core logic (Johnson, Bellman-Ford, Dijkstra modules)
test/               # Mock graph + SQL runner
CMakeLists.txt      # Build setup
```

## ⚙️ Build Instructions
```
mkdir build && cd build
cmake ..
make
sudo make install
```

## 🧪 Test Graph (Negative-weight, No Cycles)
```
CREATE TABLE edges (
    id serial PRIMARY KEY,
    source integer,
    target integer,
    cost double precision,
    reverse_cost double precision
);

INSERT INTO edges (source, target, cost, reverse_cost) VALUES
(1, 2, 3.0, 3.0),
(2, 3, -2.0, -2.0),
(3, 4, 1.0, 1.0),
(4, 1, 4.0, 4.0);
```

## 🧠 Why Johnson’s Algorithm?
Efficient on sparse graphs (typical of geospatial networks)

Handles negative weights (e.g., toll rebates, incentives)

Improves batch-routing, OD matrix generation, and analytics

## 📬 Updates
This repo will be updated regularly as the GSoC project progresses.

📅 Current Phase: Pre-selection prep (April 2025)
🧵 Devlog and progress: Coming soon...

📡 Connect
GitHub: mrvenom17
LinkedIn: [Alay Sharma](https://www.linkedin.com/in/alay-sh/)