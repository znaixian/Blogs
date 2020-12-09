## Graph Theory Basics

---
3Blue1Brown is very good youtube channel explaining complex math concepts, I am glad to see Grant - author of this channel - opened up his animation codes on github, so more and more pros joined and created superior content to par with Grant's quality. 
(by the way, Grant tweeted [Casey Li's blog explaning PCA](https://notsquirrel.com/pca/), from which, she cited the [Grant's github repo manim](https://github.com/3b1b/manim))

This blog however is not about PCA but about Graph Theory Basics, thanks to ["reducible"'s clear lectures](https://www.youtube.com/watch?v=LFKZLXVO-Dg&t=9s). 

Graph theory is widely used including navigation system, web page links, data transmission, social networks, fluid dynamics, critical pth, 3D modeling, game and simulations, air travel, topological sort DAG...But in his view, it's so unique and mind-provoking that he pointed out the sudoku problem actually is a graph one, just picuture every number from 1 to 9 a unique color, and then try to figure out arrangment of these colored dots with certain rules. There are graph algorithm already set to solve it easily. 
![](pictures/sudoku%20is%20a%20graph%20problem.png)

First, house keeping Definition and Terminology: definition of graph is "Network that hels define and visualize relationship between various components"; vertex, vertices, edges and degrees (degree(v) is equal to the number of edges connected to v), path, path length (number of edges in a path) cycle path that starts and ends at the same vertex. connectivity, two vertices connected, or a graph is connected to the other. undirected and directed graph. Directed cyclic Graph(DCG) or Directed Acyclic Graph(DAG), weighte Graph. Trees(connected and acyclic, removing edge disconnects graph, adding edge creats a cycle). 
To describe graph in programming set, you can have
- Adjacency matrix
- Edge set
- Adjancency list, the most commonly used

### Then Depth First Search(DFS)

DFS is quite intuitively understandable but to implement on coding level, there are several ways. The following graph illustrate one way a for loop 
![](pictures/dfs%20process.png)
There is an iterative approach too
![](pictures/dfs%20iterative%20process.png)
preorder and postorder

Once grasped DFS, one can solve topological sort(DAG). And he mentioned a fun application to generate maze:


### Lastly Breadth First Search(BFS)
The process is similar intuitive as DFS. There are a bunch of problems that can be solved by BFS. 

One is "Flood Fill Problem", 
![](pictures/flood%20fill%20problem.png)



