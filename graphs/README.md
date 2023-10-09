# Graphs in JavaScript

A graph is a data structure that consists of a finite set of nodes (vertices) and a set of edges that connect pairs of nodes. Graphs are used to represent various real-world relationships and networks, such as social networks, transportation systems, and more.

## Types of Graphs

There are various types of graphs, including:

- **Undirected Graph**: Edges have no direction, representing symmetric relationships.
- **Directed Graph (Digraph)**: Edges have direction, representing asymmetric relationships.
- **Weighted Graph**: Edges have weights or costs associated with them.
- **Cyclic Graph**: Contains cycles (loops) in the graph.
- **Acyclic Graph**: Does not contain any cycles.

## Operations on Graphs

Common operations on graphs include:

- **Add Node**: Adding a new node (vertex) to the graph.
- **Add Edge**: Adding an edge between two nodes.
- **Remove Node**: Removing a node and its associated edges from the graph.
- **Remove Edge**: Removing an edge between two nodes.
- **Traversal**: Visiting nodes and edges in the graph.
- **Search**: Finding a path or specific information in the graph.

## JavaScript Implementation

In JavaScript, you can implement graphs using various data structures, such as adjacency lists or adjacency matrices. Here's a simplified example of implementing an undirected graph using an adjacency list:

```js
class Graph {
  constructor() {
    this.nodes = new Map();
  }

  addNode(node) {
    if (!this.nodes.has(node)) {
      this.nodes.set(node, []);
    }
  }

  addEdge(node1, node2) {
    if (this.nodes.has(node1) && this.nodes.has(node2)) {
      this.nodes.get(node1).push(node2);
      this.nodes.get(node2).push(node1); // For an undirected graph
    }
  }

  // Other methods like removeNode, removeEdge, traversal, and search can be implemented here
}

// Usage example
const graph = new Graph();
graph.addNode("A");
graph.addNode("B");
graph.addEdge("A", "B");
```