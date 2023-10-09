# Graph Traversal in JavaScript

Graph traversal is the process of visiting all the nodes and edges of a graph systematically. It's an essential operation in graph algorithms and helps discover paths, connectivity, and other valuable information within the graph.

## Common Graph Traversal Algorithms

There are two primary methods for graph traversal:

1. **Depth-First Search (DFS)**: DFS explores as far as possible along each branch before backtracking. It's implemented using recursion or a stack.

2. **Breadth-First Search (BFS)**: BFS explores all the neighbors of a node before moving to their children. It's implemented using a queue.

## JavaScript Implementation (DFS and BFS)

Here's an example of implementing DFS and BFS graph traversal in JavaScript:

```javascript
class Graph {
  constructor() {
    this.adjacencyList = new Map();
  }

  // ... (addNode and addEdge methods from previous example)

  // Depth-First Search (DFS)
  dfs(startNode, callback) {
    const visited = new Set();

    function dfsHelper(node) {
      if (!visited.has(node)) {
        visited.add(node);
        callback(node);

        for (const neighbor of this.adjacencyList.get(node)) {
          dfsHelper(neighbor);
        }
      }
    }

    dfsHelper(startNode);
  }

  // Breadth-First Search (BFS)
  bfs(startNode, callback) {
    const visited = new Set();
    const queue = [startNode];
    visited.add(startNode);

    while (queue.length > 0) {
      const node = queue.shift();
      callback(node);

      for (const neighbor of this.adjacencyList.get(node)) {
        if (!visited.has(neighbor)) {
          visited.add(neighbor);
          queue.push(neighbor);
        }
      }
    }
  }
}

// Usage example
const graph = new Graph();
graph.addNode("A");
graph.addNode("B");
graph.addNode("C");
graph.addEdge("A", "B");
graph.addEdge("A", "C");

// DFS traversal example
graph.dfs("A", (node) => console.log(node));

// BFS traversal example
graph.bfs("A", (node) => console.log(node));
```