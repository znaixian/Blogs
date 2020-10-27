## Graphy Theory

⭐️ Course Contents ⭐️

⌨️ (0:00:00) Graph Theory Introduction
Graph theory is the mathmatical theory of the properties and applications of graphs(networks). It is used to represent almost any problem fraught almost anywhere. Types of graphs: undirected graph edges have no orientation (u, v) = (v, u), directed graph(digraph) where edges are directed. Special graphs: trees, rooted tree, DAGs, directed acyclic graphs, bipartite graph, complete graphs. 

Representing graphs on a computer, adjancy matrix m is a very simple way to represent a graph. the cell m[i][j] represents the edge weight of going from node i to node j, adjacency list, edge list.

⌨️ (0:13:53) Problems in Graph Theory
Number one, shortest path problem BFS breath first search; second connectivity problem: can one node reach another one, union find data; third, negative cycles, trading currency bellman-ford algo. strongly connected components within a graph, 

⌨️ (0:23:15) Depth First Search Algorithm
depth first search DFS, it's an algo that allows traversal, time complexity is the size of graph. DFS isn't very useful 
#global or class scope variables
codes
'''
application: finding connected components in a graph
to make all reachable nodes as being part of the same component.

⌨️ (0:33:18) Breadth First Search Algorithm
BFS are building blocks in other algos, useful for one thing, finding shortest path. expose in a layered fashion. 

⌨️ (0:40:27) Breadth First Search grid shortest path
The very first step is how to describe it in a math language
![graph on grid](../Research/pictures/graph%20theory%20on%20grids.png)
```
#define the direction vectors for north, south, east and west
dr = [-1, +1, 0, 0]
dc = [0, 0, +1, -1]
for (i = 0, i < 4, i++):
  rr = r +dr[i]
  cc = c + dc[i]
  # skip invalid cells, assume r and c for the number of rows and columns
  if rr < 0 or cc < 0: continue
  if rr >= R or cc >= C: continue
```
>Dungeon problem solving
first, statement of Dungeon problem: you are trapped in a 2D dungeon and need to find the quickest way out. the dungeon is composed of unit cubes which may or may not be filled with rock. it takes one minute to move one unit north, south, east, west. You cannnot move diagonally and the maze is surrounded by solid rock on all sides. Is an esacape possible, if yes, how long will it take?

>with aid of representative grid, the machine can figure out the path by
![shortest path for dungeon problem](../research/pictures/retracing%20the%20short%20path.png)

But there are other representive forms such as multiple queues for multiple-dimensional grid.              

⌨️ (0:56:23) Topological Sort Algorithm
Many real world situations can be modelled as a graph, examples are school class prerequisites, program dependenceis, evnet scheduling, assemble instructions etc. 
DAG directed acyclic graph can be valid topological ordering only if there is no cycles within. So all rooted trees have a topological ordering since they do not contain any cycles by definition.
Next, we'd like to see the topological sort algorithm and its codes. 
```
#assumptin: graph is stored as adjacency list
function toposort(graph):
  N = graph.number0fNodes()
  V = [false, ..., false]
  ordering = [0,...,0]
  i = N - 1 
  
  for (at =0; at < N; at++):
     if V[at] == false:
       visitedNodes = []
       dfs(at, V, visitedNodes, graph)
        for nodeId in visitedNodes
```
topsort optimization

⌨️ (1:09:52) Shortest/Longest path on a Directed Acyclic Graph (DAG)


⌨️ (1:19:34) Dijkstra's Shortest Path Algorithm
⌨️ (1:43:17) Dijkstra's Shortest Path Algorithm | Source Code
⌨️ (1:50:47) Bellman Ford Algorithm
⌨️ (2:05:34) Floyd Warshall All Pairs Shortest Path Algorithm
⌨️ (2:20:54) Floyd Warshall All Pairs Shortest Path Algorithm | Source Code
⌨️ (2:29:19) Bridges and Articulation points Algorithm
⌨️ (2:49:01) Bridges and Articulation points source code
⌨️ (2:57:32) Tarjans Strongly Connected Components algorithm
⌨️ (3:13:56) Tarjans Strongly Connected Components algorithm source code
⌨️ (3:20:12) Travelling Salesman Problem | Dynamic Programming
⌨️ (3:39:59) Travelling Salesman Problem source code | Dynamic Programming
⌨️ (3:52:27) Existence of Eulerian Paths and Circuits
⌨️ (4:01:19) Eulerian Path Algorithm
⌨️ (4:15:47) Eulerian Path Algorithm | Source Code
⌨️ (4:23:00) Prim's Minimum Spanning Tree Algorithm
⌨️ (4:37:05) Eager Prim's Minimum Spanning Tree Algorithm
⌨️ (4:50:38) Eager Prim's Minimum Spanning Tree Algorithm | Source Code
⌨️ (4:58:30) Max Flow Ford Fulkerson | Network Flow
⌨️ (5:11:01) Max Flow Ford Fulkerson | Source Code
⌨️ (5:27:25) Unweighted Bipartite Matching | Network Flow
⌨️ (5:38:11) Mice and Owls problem | Network Flow
⌨️ (5:46:11) Elementary Math problem | Network Flow
⌨️ (5:56:19) Edmonds Karp Algorithm | Network Flow
⌨️ (6:05:18) Edmonds Karp Algorithm | Source Code
⌨️ (6:10:08) Capacity Scaling | Network Flow
⌨️ (6:19:34) Capacity Scaling | Network Flow | Source Code
⌨️ (6:25:04) Dinic's Algorithm | Network Flow
⌨️ (6:36:09) Dinic's Algorithm | Network Flow | Source Code

