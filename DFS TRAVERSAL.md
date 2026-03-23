# Experiment 17(c): DFS Traversal

## Aim
To write a Python program to print DFS (Depth-First Search) traversal from a given source vertex in a graph.

---

## Algorithm

1. **Start the program**:
   - Create a graph using an adjacency list representation.
   - Add edges between vertices using the `addEdge()` function.

2. **Implement the DFSUtil function**:
   - This function will recursively visit and print each unvisited vertex.
   - Mark the current vertex as visited.
   - Recursively call `DFSUtil()` for each unvisited adjacent vertex.

3. **DFS function**:
   - Initialize an empty set to keep track of visited vertices.
   - Call the `DFSUtil()` function starting from the given vertex.

4. **Input**:
   - The user provides the starting vertex for the DFS traversal.

5. **Perform DFS traversal**:
   - Start from the given source vertex and traverse all reachable vertices using DFS.
   - Print the vertices in the DFS order.

6. **End the program**:
   - The program outputs the order of vertices visited during the DFS traversal.

---

## Program

```
from collections import defaultdict
class Graph:
	def __init__(self):
		self.graph = defaultdict(list)
	def addEdge(self, u, v):
		self.graph[u].append(v)
	def DFSUtil(self, v, visited):
		visited.add(v)
		print(v,end=' ')
		for neighbour in self.graph[v]:
		    if neighbour not in visited:
		        self.DFSUtil(neighbour,visited)
	def DFS(self, v):
		visited = set()
		self.DFSUtil(v, visited)
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)
print("Following is DFS from (starting from vertex {})".format(n))
g.DFS(n)
```

## OUTPUT

<img width="1185" height="280" alt="image" src="https://github.com/user-attachments/assets/9ca292c0-ea8a-4509-abbf-a03eeaeaaff1" />


## RESULT
Therefore, the output is the example to write a Python program to print DFS traversal from a given source vertex.
