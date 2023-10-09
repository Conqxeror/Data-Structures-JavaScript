# Graph Representation in JavaScript (Adjacency List)

Graphs can be represented in JavaScript using various data structures. One commonly used representation is the **adjacency list**, which is efficient for sparse graphs where there are fewer edges. In an adjacency list, each node in the graph is associated with a list of its neighboring nodes.

## Advantages of Adjacency Lists

- Efficient for sparse graphs with fewer edges.
- Space-efficient as it only stores information about existing edges.
- Allows quick traversal of neighboring nodes.

## JavaScript Implementation (Adjacency List)

Here's an example of implementing a graph using an adjacency list in JavaScript:

```js
class Graph {
  constructor() {
    this.adjacencyList = new Map();
  }

  addNode(node) {
    if (!this.adjacencyList.has(node)) {
      this.adjacencyList.set(node, []);
    }
  }

  addEdge(node1, node2) {
    if (this.adjacencyList.has(node1) && this.adjacencyList.has(node2)) {
      this.adjacencyList.get(node1).push(node2);
      this.adjacencyList.get(node2).push(node1); // For an undirected graph
    }
  }

  // Other methods like removeNode, removeEdge, and traversal can be implemented here
}

// Usage example
const graph = new Graph();
graph.addNode("A");
graph.addNode("B");
graph.addEdge("A", "B");
```