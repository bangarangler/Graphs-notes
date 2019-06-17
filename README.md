# Graphs

---

## 06/17/2019

## Graph:

general-purpose data structure that can be used to solve a wide variety of computing problems. It is the genera case of the trees. where edges can connect one vertex to any other, not just downward. 

Simply a set of linked data, represented by vertices and edges. There are very loose requirements regarding how vertices can be linked together, which allows us to use graphs to represent and study many different types of scenarios.

collections of related data. Like trees, except connections can be made from any node to any other node, even forming loops. Using this definition all trees are graphs, but not all graphs are trees.

1. Translate problem into graph terms cyclic, weighted, traversal vs search etc..
2. build your graph
3. traverse the graph

Adjacency List :

{A: = > B

 B: = > A,X,P,T

 X: = > B, P

 P: ⇒ X, B

 T: = > B

}

Adjacency Matrix :

good when you have weighted graphs.

Little more efficient with memory thanks to arrays.

better for really dense graph

   A     B     X     P     T

A

B

X

P

T

Time complexity to see if something is in a set O(1)

Time complexity to see if it's in a list O(n)

**nodes** : nodes in a graph are called vertexes (or vertices or verts), and the connections between the verts are called edges.

**edge** : edge denotes a relationship or linkage between the two verts.

### They can represent

- any kind of multiway relational data.
- collection of cities and linking roads.
- collection of computers on a network
- population of people who know each other and Kevin Bacon

### Directed / Undirected Graphs

if the edges are "one way" (have an arrow), graph is said to be a directed graph. If no arrows, the edges are bidirectional and the graph is an undirected graph.

### Cyclic / Acyclic Graphs

if a cycle can be formed (ex. you can follow the edges and arrive again at an already-visited vert), the graph is cyclic. Otherwise it is acyclic

### Weighted Graphs

graphs with values (weights) associated with the edges are called weighted graphs.

meaning of the weight is dependent on the type of graph. graph of road network segments might have weight represent the length of the road. Higher total weight of a route on the graph, longer the trip is. Weights can be used to help decide if a particular route should be chosen over another.

### Directed Acyclic Graphs (DAG's)

Can model many different kinds of info. Spreadsheet can be modeled as a DAG, with a vertex for each cell and an edge whenever the formula in once cell uses the value from another; a topological ordering of this DAG can be used to update all cell values when the spreadsheet is changed. Similarly, topological orderings of DAG's can be used to order the compilation operation in a makefile.

*git* uses a DAG to represent commits. A commit can have a child commit, or more than one child commit (in the case of a branch). A child could come from one parent commit, or from two (in the case of a merge). But there's no way to go back and form a repeating loop in the git commit hierarchy.

## Breadth-First Search (BFS)

Explores the graph outward in rings of ever increasing distance from the starting vertex.

algorithm never attempts to explore a vert that it either has explored or is exploring.

Can be a good strategy for searching a graph, there are some scenarios where BFS is inefficient (ex. if target node is near the bottom of a tree) To optimize performance of applications, it is important to understand when using depth-first search (DFS) will produce better results.

good key word.... anything that is shortest path/ quickest path.

### Uses of BFS

- pathfinding, routing
- find neighbor nodes in a P2P network like Bittorrent
- web crawlers
- fining people in connections away on a social site
- find neighboring location on graph
- broadcasting in a network
- cycle detection in a graph
- finding connected components
- solving a number of theoretical graph problems.

In BFS, it's useful to track which nodes we need to follow up on. 

Can rack that by adding neighbors to a queue, and then exploring the verts in the queue.

## Depth-First Search (DFS)

Dives down the graph as far as it can before needing to backtrack and explore another branch. The algorithm never attempts to explore a vert that it either has explored or is exploring.

*Applications of DFS*

- finding minimum spanning trees of weighted graphs
- path finding
- detecting cycles in graphs
- topological sorting, useful for scheduling sequences of dependent jobs
- solving and generating mazes

*Coloring Vertexes*

Useful to color verts as graph is explored. Commonly, unvisited verts are white, verts whose neighbors are being explored are gray, and verts with no unexplored neighbors are black.

## Recursion

Since we want to pursue leads in the graph as far as we can, and then "back up" to an earlier branch point to explore that way, recursion is a good approach to help "remember" where we left off.