Airport Route Optimization and Network Analysis
This project provides a comprehensive Python-based toolkit for analyzing airport flight networks. It utilizes real-world data from OpenFlights to construct a graph representation of global aviation routes, allowing for shortest-path calculations, connectivity analysis, and network resiliency simulations.
Key Features
• Graph Construction: Builds a directed graph using AirportID as nodes and flight routes as edges, with edge weights calculated as geographic distances (Haversine formula).
• Search & Traversal:
• Breadth-First Search (BFS) and Depth-First Search (DFS) for network exploration.
• Identification of Connected Components to find isolated airport clusters.
• Shortest Path Algorithms:
• Dijkstra’s Algorithm: Reliable shortest path finding for non-negative weights.
• Bellman-Ford Algorithm: Shortest path calculation with cycle detection capabilities.
• A* Search: Optimized shortest path search using Haversine distance as a heuristic.
• Resiliency Simulation: A simulate_closure function to evaluate the impact of a hub shutdown on the rest of the network.
• Visualization: Sub-network visualization using NetworkX and 
Matplotlib, featuring degree-based coloring and curved edge layouts.
Project Structure
• 	airports.csv: Contains airport geographic data (ID, Latitude, Longitude, etc.).


• 	routes.csv: Contains airline route connections between Source and
Destination airports.
• 	main.py (or Jupyter Notebook): The primary logic for data processing,
algorithm implementation, and visualization.
Algorithms Explained
Dijkstra
Guarantees the shortest path between two airports by exploring the closest unvisited neighbors first. It is highly efficient for large flight networks.
A* (A-Star)
An extension of Dijkstra that uses a heuristic to guide the search. In this project, we use the Great-Circle (Haversine) Distance as the heuristic to significantly speed up search times toward a specific destination. The Haversine formula is defined as:
d = 2r arcsin (	sin 2 (	ϕ−ϕ	2 	1 )	+ cos(ϕ) cos(ϕ) sin 2 (	2 	1 ))
λ−λ
Where  represents latitude,  represents longitude, and  is the Earth's radius.
Bellman-Ford
Used for finding the shortest path while also checking for the presence of negative-weight cycles (though weight in this context—distance—is always positive).
Installation & Setup
1. Clone the repository: bash git clone https://github.com/your-
username/airport-network-analysis.git cd airport-
network-analysis



2. Prepare the Data: Ensure airports.csv and routes.csv 	(OpenFlights format) are in the root directory.
3. Install Dependencies: bash pip install -r requirements.txt
4. Run the Analysis: bash python main.py
Visualization Example
The project includes a plot_subset utility that generates a visual map of a portion of the network: - Node Color: Represents the "Degree" (total connections) using the Viridis colormap. - Curved Edges: Ensures overlapping routes are visible. - Layout: Uses a Spring Layout for optimal spacing.
Requirements
To run this project, you need the following Python libraries: - pandas - 
numpy - networkx - matplotlib
(See requirements.txt for details)
