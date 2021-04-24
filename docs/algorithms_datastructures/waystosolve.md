---
layout: default
---
# Ways to Solve Algorithmic Problems

## Brute Force

Just check all combinations

## Recursion

Looks simple but main trick is simplifying the base case and recursive call so that there are not a lot of base case and not a lot of if and else conditions. If not done properly then the code will be hard to understand and debug (know why it works or it does not work). Step back and use copy and pen to find the most simple base case and as less number of base cases as possible. Try to see what all things should go inside the recursive method and what should stay outside.

## Recursive vs Iterative

Performing loop using recursion vs performing loop using while.

## Backtracking

Same as Brute force but it stops in the middle of the path as soon as it seems like it won't work. It also stops any future steps from going through that sub path. Might look like dynamic programming but it is not. This technique works for problems whose solution can only be checked at the end e.g. sudoku. And generally they involve finding all possible solutions. This is much better than the naive approach of trying all possible combinations. Backtracking removes the solution (prune the branch) as soon as it sees that it won't lead to a solution so that you don't have to go that path in future.

## Greedy Algorithm

More like dynamic programming but once the decision is made on the subproblem using local information it is not changed. Subproblems are independent. In dynamic programming the solution to subproblems are revised based on new information as you progress.

e.g.

1. Fractional Knapsack - take the ratio of value/weight and start taking the one with max ratio until the Knapsack is either full or that item is consumed. Then start with the one with next max ratio and so on.

2. Dijkstra's algorithms - It has a dynamic programming component to it but it idea it is greedy because each local solution (vertex) is solved first and then only after it is solved the next node is solved for.

## Incremental
E.g. Insertion sort - Take one element and put it in the correct place in the already sorted sub array. This technique is in contrast to divide concur.

## Divide and Concur

Similar like dynamic programming but the subproblems are substantially smaller say half the size. So the depth of the tree is logirithmic. Recursion works here because of this low depth. While in dynamic programming, the sub problem are  only slightly smaller like F(i-1) is sub problem of F(i).  Here the depth is polynomial and recursion is disastrous. Also, dynamic programming's sub problems are repeated while generally divide and concur's are disjoint.

## Dynamic Programing

Two ways to do this:

- Top to bottom - Solve sub problems to solve the bigger problem and store the solution to sub problems on the way so that if needed you don't have to calculate the sub problem again. The storing is called Memoization. This way is nothing but recursion enhanced by memoization

- Botton to top - Still uses memoization but this is done in a different order. This order is more organic/natural and is generally efficient though harder (sometimes impossible) to find since it is not easy to predict which sub problem to start with.

\- [Reference from stackoverflow](https://stackoverflow.com/questions/3592943/difference-between-back-tracking-and-dynamic-programming/26439292)

As per Umesh Vazirani, you can imagine each and every dynamic problem as a DAG (directed acyclic graph) where the nodes are sub problems and reaching from starting point to end is traversing the graph. The edges are dependencies between sub problems. <sup>[ref](https://people.eecs.berkeley.edu/~vazirani/algorithms/chap6.pdf)</sup>

In dynamic programming the key is to find the sub problem and the set of base cases. You can imagine progressing a dynamic programming problem either like a DAG or like a table structure (or cube or even higher dimensions) each dependency is one dimension.

Common subproblems - Finding the right subproblem takes creativity and experimentation. But there are a few standard choices that seem to arise repeatedly in dynamic programming.

The toughest part of this is finding the sub problems. It might take a little hit and trial and patience.

Problems to practice:

1. Knapsack (with repetition and without repetition)
2. Traveling Salesman Problem
3. Shortest/Longest Path (additional twists - pair wise, limited edges)

Principle of Optimality

e.g If shortest path from A > E is A>B>C>D>E then the sub path C>D in this route used will be shortest between C>D.
Longest path algo does not follow Principle of Optimality. Take a cyclic graph for example.

\- [ref](https://www2.seas.gwu.edu/~ayoussef/cs6212/dynamicprog.html)

e.g.

0-1 Knapsack Problem -

Capacity = W
w1, w2, w3, w4
v1, v2, v3, v4

Let us start from the back:

Take max of - considering w4 or not

K(<w1, w2, w3, w4>, W) = Max[ K(<w1, w2, w3>, W), K(<w1, w2, w3>, W - w4) ]

## Genetic Algorithm

## Binary Search ($$\log n$$ complexity)

Eliminating half of the input at each step to finally reach the target.

## Graphs

Represented as G(V,E) => V is vertex names and E is pair wise Vs representing edges.


## Stars and Bars

Problem statement:
How to put all N balls in K buckets
or
How to partition N identical items in K-tuples

Natural way to solve - After several tries it seems the normal way of combinatorics is not possible.
1. Take 1 bucket > 1 way : N
2. Take 2 buckets > N + 1 ways : 0-(N), 1-(N-1), ... (N)-0
3. Take 3 buckets >

Better is the way of stars and bars. Imagine x below is a star

$$xxxx|xxx|xx||xx$$

Each bars above separates the balls into buckets. So for 5 buckets we need 4 bars. If we want the bucket to be empty then keep it either at the end of adjacent to another bar. Total placeholders including both stars and bars = N+K. Now this question has been turned into finding the total number of ways in which we can put these bars. Remember that the bars are identical themselves (this does not mean that the buckets are identical).

Hence total number of ways = $$^{\small{N+K}}C_{\small{K-1}}$$

## Proving the correctness of Algorithm

Let me start with an example. Suppose you are using a broom to clean the floor of a room. You can clean it going row by row (north to south) starting at the east and ending at the west. You may also start from the center and keep going outwards in a spiral (slowing overlapping your sweeps so that the circle becomes a square. This is not important here but just to be clear). There are many other ways too. These ways will be preferred compared to just going in patches or randomly because it is hard to track what is left and where are the overlaps. It is easy to see that going row by row will eventually clean the whole floor. Why? Because we can see that at any point in time, there is a section of the room which is clean and we are not leaving anything in that section when cleaning. Each row covers more swept floor without leaving anything in that row. This is called as "loop invariant". Using this concept it is easier to proof that a algorithm with end correctly. The pattern is more like mathematical induction which we learned in high school. Let me formalize here:

1. Initialization - Loop invariant is present at the start.

2. Maintenance - Loop invariant is maintained at the end of each iteration.

3. Termination - Whole input is traversed.

## $$\Theta$$ (Big Theta) - asymptotic upper & lower bound

If a function $$f(n)$$ can be sandwiched between $$c1(g(n))$$ and $$c2(g(n))$$ for all values greater than a specific value of $$n$$.

## $$O$$ (Big O) - asymptotic upper bound
x² ∈ O(x² + x)

## $$\Omega$$ (Big Omega) - asymptotic lower bound

## $$o$$ (little o) - asymptotic upper bound (not tight)
x² ∈ o(x³)

## $$\omega$$ (little omega) - asymptotic lower bound (not tight)

## Theorem
$$f(n) = \Theta(g(n))$$ if and only if
$$f(n) = O(g(n))$$ and $$f(n) = \Omega(g(n))$$

This theorem is not useful when going from theta to omega and O. It is useful trying to find theta based on omega and O.

## Fibonacci Number
if $$\phi$$ and $$\hat\phi$$ are roots of $$x^2 = x + 1$$ then

F_i = $$\frac{\phi^i + \hat\phi^i} {\sqrt{5}}$$

## Inclusion-Exclusion Principle

$$|A\cup B\cup C|=|A|+|B|+|C|-|A\cap B|-|A\cap C|-|B\cap C|+|A\cap B\cap C|$$

## Solving maximum bipartite matching by converting to network flow -

https://www.cs.cmu.edu/~ckingsf/bioinfo-lectures/matching.pdf

## Multi array - How to iterate


## Convert bipartite to max flow

- ford fulkerson > residual graph > negative weights

## Max Flow

Simple greedy algorithm of passing what max is possible through each possible path does not give optimal solution.

Augmenting Path - Path from source to sink using edges whose capacity is not completely used yet.

find the bottle neck

Keep going until no such path is found

Residual Graph - Main idea - We are given flow/capacity of each edge and its direction. Imagine that there is something on the opposite direction too like 0/(-capacity). It is like assuming that the backward capacity is zero and no flow is used there. This updated graph with additional backward graph is called residual graph. This is mainly to undo the bad choices later.

Ford Fulkerson - Use DFS to find augumenting paths but this can show slowness as findiing the path is random.

Edmund-Karp - Works better because it uses BFS - Need to read more on why

Capacity Scaling - Use the longest paths fist so that the remaining edges to be considered is less

You can send whatever flow you want in either direction subject to condition that flow in forward edge will not be negative and the capacity in the forward edge will not be negative.

## Min cut

Is theoretically same as max flow - it is the minimum amount of flow which if removed from the graph will disconnect source and sink

## P vs NP Complete

Class P Problems - Something which can be solved in polynomial time. Order of the solution is polynomial. Not an issue and considered easier.

Class NP Problems - It stands for non deterministic and not non polynomial. Finding solution may or may not take polynomial time (like n!) however checking the solution for correctness takes polynomial time.

Class NP Complete - A set of NP problems which can be converted into each other in polynomial time.

Class NP Hard - Solving is atleast as hard as NP Complete

## Rejection sampling

Mapping 49 numbers which can appear in equal probability on 10 numbers. If it was 50 then you could map 1,11,21,31 and 41 to 1 and etc. But with 49 how can you manage? You can map 1-40 of 49 to 10 and if any number which is not in range like 42 comes then try again unless the number comes in the range of 1-40.

e.g. https://leetcode.com/problems/implement-rand10-using-rand7/solution/

## Hamming distance

Applicable only for strings of same length. Only substitution allowed. Number of digits which are different between two strings:

e.g.

habpy
sappi

hamming distance of 3

## Levenshtein distance

Substitution, Insertion and deletion allowed. Minimum number of single-character edits (insertions, deletions or substitutions) required to change one word into the other.

kitten & sitting = 3
kitten > sitten (substitution of "s" for "k")
sitten > sittin (substitution of "i" for "e")
sittin > sitting (insertion of "g" at the end)

Algorithm:

E.g. BARK and CARRY

Get min of following 3 (Take one string as base string and then start from the back. And then keep going recursive)

1. Insertion - BARKY & CARRY
2. Deletion - BAR & CARRY
3. Substitution - BARY & CARRY

## Longest common subsequence

Only insertion and deletion allowed

n^2 are normal algorithm - either start from front or back.

FRONT

729734
   i

the cursor i keep moving from 0 to len-1 and checks against all the indexes before it. In the example above i = 4. So it will check as follows:
1. if 7 > 7 then f(4) = 1 + f(1) else f(4) = f(1)
2. if 7 > 2 then f(4) = 1 + f(2) else f(4) = f(2)
.
.
.
take max of above numbers and that is f(4)s

BETTER Algo - nlogn - use patience sort as explained below:

https://www.youtube.com/watch?v=22s1xxRvy28

## Longest common substring

longest Substring common to all given subsequences.

## tree traversal using dfs
Recursive solution to following is quite straghtforward

## preorder
node > left > right

while stack:
    curr = stack.pop()
    output.append(curr.val) #visit node

    if curr.right:
        stack.append(curr.right)
    if curr.left:
        stack.append(curr.left)

## inorder
left > node > right

while stack:
    if curr.left:
        curr = curr.left
        stack.append(curr)
    else:
        curr = stack.pop()
        output.append(curr.val) #visit node
        if curr.right:
            curr = curr.right
            stack.append(curr)

One problem with the above is that we are not maintaining the visited nodes so as we are resolving and moving up, the logic will again try to take us to the bottom of the tree. This issue can be resolved using a visited map like below:

while stack:
    if curr.left and curr not in visited:
           curr = curr.left
           stack.append(curr)
       else:
           curr = stack.pop()

           output.append(curr.val)
           visited[curr] = True
           if element_found:
               return curr
           if curr == p:
               element_found = True

           if curr.right:
               curr = curr.right
               stack.append(curr)

## postorder
right > left > node

Similar to above. Just swap left and right

## Union - find algorithm

Works in graphs to group nodes into subsets. Works as follows:

1. Put each element into a separate group to start with.
2. Loop on edges
   3. e.g. union(A,B) => find A's parent (which is established in step 1 above) and make that B's parent.

Path compression - all subset members point to the same parent.

## MIPS or FLOPS/MFLOPS/GFLOPS

MIPS - millions of instructions per sec

MFLOPS - Millions of floating point calculations per sec

Today's computers are around 50-100 GFLOPS

## Amortized Analysis

Average of complexity - Needed because some operations are kicked in only at specific time/case. E.g. Arrays, they have an extra operation when it doubles it size.

## Boyer-Moore Voting Algorithm

Helps in finding the majority element in a array in shortest time using O(1) space.

1. Keep going one element by one element

2. Cancel out the majoritty with all minorty elements and as soon as it becomes zero, start again.

https://www.youtube.com/watch?v=AoX3BPWNnoE - start from 3:30
