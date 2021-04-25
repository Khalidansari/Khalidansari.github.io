# Graph Theory

## Graph vs Tree vs Binary Tree

A structure where nodes are connected to each other through edges is called a graph. Tree is something which is a special case of graph with parent child relation between nodes. Binary tree is a special case of tree where parent is allowed to have maximum of two children.

## Graph Coloring

Coloring vertices such that no two adjacent vertices are of the same color. The coloring can also be done for edges or faces but need not be studied separately as they can be converted to vertex coloring.

## Red Black Tree

## Binary Search Tree

## Maximum Flow

## Euler Path vs Euler Circuit

Euler Path is when you visit "every" edge "only once". This is possible only if all its vertices are even. Euler circuit is a special case of Euler Path where start node is same as end node. This is possible only if only two of its vertices are odd.

## Hamiltonian Path vs Hamiltonian Circuit

Same as Euler Path/Circuit above except that the constraint is on vertex instead of edge. There is no necessary and sufficient set of condition here like Euler Path/Circuit.

## Shortest Path

 - Dijkstra's algorithm solves the single-source shortest path problem with non-negative edge weight. Because the path which is looking longer now may become shorter if a negative edge appears. 
 - Bellman–Ford algorithm solves the single-source problem if edge weights may be negative.
 - Floyd–Warshall algorithm solves all pairs shortest paths.

## Minimum Spanning Tree

## Traveling Salesman Problem

## Bipartite

## 4 Color Theorem

## DFS vs BFS

BFS - Visit all nodes at the current level before going deeper

DFS - Keep going down the tree until you hit the leaf and then backtrack and go deeper through another path.

preorder - Main Node > Left Subtree > Right Subtree
inorder  - Left Subtree > Main Node > Right Subtree
post order  - Left Subtree > Right Subtree >  Main Node

[![](http://img.youtube.com/vi/zaBhtODEL0w/0.jpg)](http://www.youtube.com/watch?v=zaBhtODEL0w "DFS vs BFS (HackerRank)")

## Other terms - Forest, etc.
