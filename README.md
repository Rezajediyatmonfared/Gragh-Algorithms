# Airport Network Analysis

## Project Overview

This project analyzes an airport and flight route network using graph theory and shortest path algorithms. It loads real-world airport and route data, constructs a directed weighted graph, and applies classical algorithms such as BFS, DFS, Dijkstra, Bellman-Ford, and A* to study connectivity and route optimization.

The project also includes:

- Connected component analysis
- Airport closure simulation
- Network visualization
- Geographic distance calculation using the Haversine formula

---

## Features

- Graph construction from airport and route datasets
- Geographic distance calculation using latitude and longitude
- Breadth-First Search (BFS)
- Depth-First Search (DFS)
- Connected components detection
- Dijkstra’s shortest path algorithm
- Bellman-Ford algorithm
- A* search algorithm
- Airport closure simulation
- Subset network visualization

---

## Dataset

The project uses the following OpenFlights datasets:

- `airports.csv`
- `routes.csv`

### Airport Data

Each airport record includes:

- Airport ID
- Name
- City
- Country
- IATA / ICAO codes
- Latitude
- Longitude
- Altitude
- Timezone
- Type
- Source

### Route Data

Each route record includes:

- Airline
- Airline ID
- Source airport
- Source airport ID
- Destination airport
- Destination airport ID
- Codeshare
- Stops
- Equipment

---

## Methodology

### 1. Data Preprocessing

- Missing values are removed from critical columns.
- Airport and route IDs are converted to integer type.
- Cleaned data is used for graph construction.

### 2. Graph Construction

- Airports are stored in a dictionary as:
  - `AirportID -> (Latitude, Longitude)`
- Flight routes are stored as a directed adjacency list:
  - `SourceAirportID -> [(DestAirportID, Distance), ...]`

### 3. Distance Calculation

The Haversine formula is used to compute the great-circle distance between two airports.

### 4. Search Algorithms

- BFS is used to explore the network level by level.
- DFS is used for deep traversal of the graph.
- Dijkstra finds the shortest weighted path.
- Bellman-Ford also finds the shortest path and can detect negative-weight cycles.
- A* uses geographic distance as a heuristic to speed up path finding.

### 5. Network Analysis

- Connected components are computed by converting the directed graph into an undirected representation for connectivity analysis.
- A closure simulation function is used to remove a hub airport and inspect the effect on the network.

### 6. Visualization

- A subset of the airport network is visualized using NetworkX and Matplotlib.
- Nodes are colored based on degree.
- Curved edges are used for better readability.

---

## Requirements

Install the required Python libraries:
```bash
pip install -r requirements.txt
