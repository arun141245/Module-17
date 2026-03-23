# Experiment 17e: Topological Sort

## Aim
To write a Python program to print the topological sorting of a Directed Acyclic Graph (DAG).

---

## Algorithm

1. **Create a graph**: 
   - Represent the graph using an adjacency list where each node points to its adjacent nodes (edges).

2. **DFS Traversal**:
   - Use a DFS approach to traverse the graph. Keep track of visited nodes to avoid revisiting them.
   - For each node, explore all its neighbors recursively.

3. **Departure Array**:
   - Maintain an array to record the nodes in reverse order of their completion times. This will represent the topological order.

4. **Topological Sort**:
   - After DFS completion for all unvisited nodes, print the nodes in the reverse of the departure array to get the topological sorting.

5. **End the program**:
   - Print the topological order of the nodes.

---

## Program

```
def addEdge(u, v):
	global adj
	adj[u].append(v)
def DFS(v):
	global visited, departure, time
	visited[v] = 1
	for i in adj[v]:
		if visited[i] == 0:
			DFS(i)
	departure[time] = v
	time += 1
def topologicalSort():
    for i in range(V):
        if visited[i]==0:
            DFS(i)
    for i in range(V-1,-1,-1):
        print(departure[i],end=" ")
if __name__ == '__main__':
	V,time, adj, visited, departure = 6, 0, [[] for i in range(7)], [0 for i in range(7)],[-1 for i in range(7)]
	addEdge(5, 2)
	addEdge(5, 0)
	addEdge(4, 0)
	addEdge(4, 1)
	addEdge(2, 3)
	addEdge(3, 1)
	print("Topological Sort of the given graph is")
	topologicalSort()
```

## OUTPUT
<img width="1183" height="217" alt="image" src="https://github.com/user-attachments/assets/79fbd919-29ee-47b5-9b83-b8aebc1ea291" />

## RESULT
Therefore, the output is the example to write a Python program to print topological sorting of a Directed Acyclic Graph (DAG).
