---
layout: default
---
# Ways to Solve an Algorithmic Problems

## Dynamic Programing

Two ways to do this:

- Top to bottom - Solve sub problems to solve the bigger problem and store the solution to sub problems on the way so that if needed you don't have to calculate the sub problem again. The storing is called Memoization. This way is nothing but recursion enhanced by memoization

- Botton to top - Still uses memoization but this is done in a different order. This order is more organic/natural and is generally efficient though harder (sometimes impossible) to find since it is not easy to predict which sub problem to start with.

\- [Reference from stackoverflow](https://stackoverflow.com/questions/3592943/difference-between-back-tracking-and-dynamic-programming/26439292)

As per Umesh Vazirani, you can imagine each and every dynamic problem as a DAG (directed acyclic graph) where the nodes are sub problems and reaching from starting point to end is traversing the graph. The edges are dependencies between sub problems. <sup>[ref](https://people.eecs.berkeley.edu/~vazirani/algorithms/chap6.pdf)</sup>

In dynamic programming the key is to find the sub problem and the set of base cases. You can imagine progressing a dynamic programming problem either like a DAG or like a table structure (or cube or even higher dimensions) each dependency is one dimension.

Common subproblems - Finding the right subproblem takes creativity and experimentation. But there are a few standard choices that seem to arise repeatedly in dynamic programming.

## Backtracking

Might look like dynamic programming but it is not. This technique works for problems whose solution can only be checked at the end e.g. sudoku. And generally they involve finding all possible solutions. This is much better than the naive approach of trying all possible combinations. Backtracking removes the solution (prune the branch) as soon as it sees that it won't lead to a solution so that you don't have to go that path in future.

## Greedy Algorithm


## Divide and Concur

Similar like dynamic programming but the subproblems are substantially smaller say half the size. So the depth of the tree is logirithmic. Recursion works here because of this low depth. While in dynamic programming, the sub problem are  only slightly smaller like F(i-1) is sub problem of F(i).  Here the depth is polynomial and recursion is disastrous. Also, dynamic programming's sub problems are repeated while generally divide and concur's are disjoint.

## Genetic Algorithm


## Backtracking
