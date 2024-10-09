# **Traffic Flow Prediction; Italy Road Networks**
Mahade Mishuk

<img width="600" alt="Screenshot 2024-10-09 at 1 22 48 AM" src="https://github.com/user-attachments/assets/edd7faf5-dc34-4148-8b67-70b72e9ce24b">

**1. Introduction**

Traffic congestion is a significant issue in urban areas, leading to delays, increased fuel consumption, and environmental pollution. Accurate traffic flow prediction is essential for effective traffic management, urban planning, and improving road safety. 

This network consists of nodes representing different locations in Italy and edges representing roads connecting those spots. 
In this project, the road network of Italy is represented as a graph, where intersections (nodes) are connected by roads (edges). This allows us to analyze the network using deep learning graph theory and machine learning techniques, and to simulate how different factors—such as road closures—affect traffic flow. Furthermore, we implement a Graph Convolutional Network (GCN) to predict traffic flow based on node-level traffic data.


**2. Data Description**

The dataset used in this project is sourced from the Purdue University Network Repository (https://networkrepository.com/index.php). The dataset used for this project comprises traffic flow data from the Italy road network. The edges represent roads, and the nodes signify intersections.

<p align="center">
  <img width="255" alt="Screenshot" src="https://github.com/user-attachments/assets/adb9bb14-77b7-4135-ae3f-901bf1d88506">
  <img width="255" alt="Screenshot" src="https://github.com/user-attachments/assets/46befa65-0615-422d-b781-22993b60c58d">
  <img width="255" alt="Screenshot" src="https://github.com/user-attachments/assets/13ed5498-dfca-4302-b0e8-db49a2dfefdf">

</p>


Note: The actual dataset was quite large with millions of edges (size: 32MB), which take a long time to run, so I had to cut and keep only in specific small area's edges (thousands of edges) to work faster.


**3. Methodology**

NetworkX library <br>
matplotlib <br>
Louvain modularity algorithm <br>
Dijkstra’s algorithm <br>
Graph Convolutional Network (GCN)






**4. Implementation**

- Graph Representation of Road Network The road network is modeled as a graph using the NetworkX library, where nodes represent locations in Italy, and edges represent the roads connecting these locations.
- Network Statistics: Calculated the number of nodes and edges to give a basic understanding of the network size.
- Centrality Measures Centrality measures help identify the most important nodes in the network.

  - Degree Centrality: Measures how many connections a node has.
  - Betweenness Centrality: Measures how often a node acts as a bridge along the shortest path between two other nodes.
  - Assortativity measures the tendency of nodes to connect to other nodes that are similar in some way. We got negative assortativity value that suggests a preference for hubs to connect to less connected nodes. While a positive assortativity indicates that nodes tend to connect to other nodes with similar degrees.
 
- Community Detection: To explore the structure of the road network, I used the Louvain modularity algorithm to detect communities (clusters of closely connected nodes) in the graph. These clusters represent groups of roads that are more densely connected than the rest of the network.
- Simulating Road Closures: To assess the impact of road closures on the network, simulated the closure of selected roads and evaluate the resulting changes in the network structure, such as recalculating the number of connected components.
- Shortest Path Prediction Using Dijkstra’s Algorithm: used Dijkstra's algorithm to compute the shortest path between two locations in the road network. This is crucial for traffic flow prediction, as finding efficient routes can alleviate congestion.
- Traffic Flow Prediction Using Graph Convolutional Networks (GCNs) For the final step, predicted traffic flow using a GCN, which is a type of neural network designed for graph-structured data. Each node in the graph is assigned a traffic feature (randomly simulated in this case), and the GCN is used to predict traffic levels at each node based on the graph structure.


**5. Results**

The project successfully modeled the road network and provided insights into key locations and their significance in traffic management through centrality measures. Community detection highlighted clusters of interconnected roads, which can be useful for planning and identifying potential traffic bottlenecks. The simulation of road closures demonstrated how such events affect network connectivity. Finally, the implementation of a GCN offers a framework for predicting traffic flow at various points in the network based on real-time data.

**6. Conclusion**

The GCN model allows for predictive analysis of traffic conditions on a large road network, while graph-based metrics like centrality and clustering provide valuable insights into the network structure. Further work can involve using real traffic data to refine predictions and explore more advanced models for traffic management applications.

**7. References**

Data: https://networkrepository.com/road.php

images: downloaded from internet.
