---
layout: default
---
# Adhoc Tricks

## Run JD decompiler on mac

CD to the directory with the JD jar and then run the following command:

> java --add-opens java.base/jdk.internal.loader=ALL-UNNAMED --add-opens jdk.zipfs/jdk.nio.zipfs=ALL-UNNAMED -jar jd-gui-1.4.0.jar

## Declarative and Imperative

Declarative = focus on what needs to be achieved
Imperative = focus on how to achieve it. It comes from grammar where it means a command or a request to do something.

Imperative uses steps to change the state.

Procedural = is a layer on top of Imperative which localizes and modularizes steps so that it can be reused. In one way it is a step which connects Imperative and Declarative as the programmer need not look at the steps inside a function to see how a certain thing is done but can understand just by looking at the name/arguments of a function.

Turing machines / processors / native code all run in imperative way. Even real life tasks like recipes which makes imperative very natural to humans.

## Timeline of languages

ALGOL - (1958) - First to use for, while, etc.

Fortan (57) - people were reluctant that it won't have the performance of hand coded Assembly language but once they saw program lengths getting shorter by a factor of 20, they adopted it. Has loops but not for.

LISP (1958) - First language with full lambda features

COBOL (1960) - Industry, scientists and government (specially dod) joined to create a specification for a new language which can work on all computers (portable)

BASIC (1964) - Dartmouth college created a easier language so that their student can learn programming. It became popular for various reasons. Microsoft created a microcomputer version of BASIC and included that in their PCs; Students already knew the syntax and there was a familiarity; it was high level enough to be used by hobyists, it was small enough to be added to personal computers.

PASCAL/C

C++ (1983)

python (1990)

PHP (1994)

Java (1996)

1G - first generation languages - Machine code
2G - Assembly
3G - High level language

## Interpreted vs Compiled languages

Compiled languages are more strict (e.g. static typing) during compilation because there is no catch during the runtime. However Interpreted languages are dynamic because they can catch and stop incorrect execution during runtime. Security wise this is good because running compiled code which is not yet vetted is dangerous.

Hence Interpreted languages are good for prototype while compiled are good for running and distributing code programs.

## Structured Programming

1. Blocks - First came in ALGOL in 1950s. Various languages implement in various ways (indentation, curly braces, special words like if else if). This helps in keeping one set of code together so that the outer program can treat it like a single statement. Also, it helps in establishing the lexical scope of variables.

2. Subroutines

3. Control flow - IF/Else, For, While

Structured program theorem, also called the Böhm–Jacopini theorem -  Any computable function can be computed by running subroutines in combination of following. Sort of a proof that we don't need goto.

1. Run in series
2. Run based on condition
3. Run in loop till a condition meets

The above makes sure the program runs linearly and each block has one exit point. However, even modern languages bypass this by using the Following
```java
continue;
break;
and early return statements
throwing error in try catch can also derail the linear flow - Can make it hard to analyze all possible flows of the program based on inputs. It is argued by Jim Bonang that Ariane 5 disaster was caused by this design.
```
error handling - They create hidden control-flow paths that are difficult for programmers to reason about.

Also, in addition to early exit there is another case of arbitrary entry. In single thread it is okay because the program will continue from where it left off but in case of multiple threads the state might have changed by time it comes back. And thus introduce a different form of complexity.

## Modular Programming

Creating independent modules which can operate a particular feature independently. Interaction only through well defined interfaces with each other. If modules are nodes then it should ideally form a Directed Acyclic Graph. If there is a cycle then it might be an indication that all modules in the cycle should form a single module.

In OOPs the interfaces helps keep the modules separate and only connect to each other through interfaces

## Assembly Language

Is any low-level programming language in which there is a very strong correspondence between the instructions in the language and the architecture's machine code instructions.

## Enable unidentified apps to run, enable Anywhere option in MAC:

> sudo spctl --master-disable
> sudo spctl --master-enable

## css more tricks -

display:grid is very useful
will-change - giving browser a headsup.

## Firebase

Google cloud app which helps deverloper with database, analytics, etc.

## Serverless computing

No dedicated server. Load managed by provider and customer is charged per usage.

## Ansible
Automation tool. Agentless > Talk through ssh

## Ansible Tower

Comes with Ansible and a web app which helps manage roles, playbooks, etc.

## Long polling vs WebSocket

HTML5 has the option to keep a WebSocket open for push notifications. Older technologies used long polling technique which was more like a workaround. This would not return the response but would keep it open for a long time before closing it and firing another one.

## Jenkins

Comes with many preinstalled plugins but one useful one is "Build Pipeline" which lets you connect the projects in a sequence and lets you see it in that way.

## Difference between CI and CD

CI = Continously integration/checkin in your code to the master + Running your unit tests/automated tests. Code should always be in prod ready state.

C Delivery = CI + Deployment to prod which might be manual

C Deployment = deployment to prod is automated

## Functional programming

Functions are first class citizen - functions are objects

higher order functions - functions can take and return other functions as parameters. Higher order functions help e.g. the below takes each element of arr1 and multiplies with 2 and makes a new arr2. The below is using array.prototype.map

const arr2 = arr1.map(item => item * 2);

The below is using array.prototype.filter. This gets all persons whose age is more than 18.

const fullAge = persons.filter(person => person.age >= 18);

Array.prototype.reduce. Takes a reducer function which takes accumulator, currentvalue, etc.

const sum = arr.reduce(function(accumulator, currentValue) {
  return accumulator + currentValue;
});



## JS Closure

Function bnundled with its lexical scope. The function can use the variable outside it. This is calculated (including the variable) during runtime when the function is called.

## Javascript Curry

Taking multiple parameters one at a time

## JS Partial app

A function with some parameters fixed in its closure scope.

## JS ES6 Spread Operator - Spread, combine and expand

const numbers = [5, 7, 3];
// Yuck!
Math.max(numbers[0], numbers[1], numbers[2]);
// And this won't work
Math.max(numbers); // NaN

// ES^ way - Much Better!
Math.max(...numbers); // 7

const one = [1,2,3];
const two = [4,5,6];
const merged = [...one, ...two];
// [ 1, 2, 3, 4, 5, 6 ]

## variadic functions
Which can take variable number of arguments, even infinity. e.g. Math.max

## JS What is generator function function*

## What is ES6?

## BFS - Breath First Search & DFS
BFS - Search the nodes at same level before moving to the next level.
DFS - Keep going to the last node in the same hiearchy. Then backtrak and go to neighbour

## Priority queue
Like a queue but can take priority of the element too.

## maximum flow problem & maximum matching

## Salesforce License categories

Permissions are like locks and licenses are like ring of keys

1. User License - Base permissions for a user. Only one per user.
   a. Standard User
      i. Salesforce - provides all functionality for internal users
      ii. Knowledge Only - Manage articles and other Knowledge related information. No access to other Standard tabs.
      iii. Identity - Identity for internal users
      iv. External Identity - Identity for External users
      v. Work.com only - to get access only to work.com and not salesforce.

2. Permission Set License - Same as profile but can be assigned incrementally on user.
3. Feature License - Generally can be assigned through a checkbox on user record or through some steps of configuration from setup
4. Usage Based License -
  a. Persistent - Number of users who can login to portal. You assign permission once and they can login as many times. These persist with user.
  b. Non-persistent - Like credit card. How many records you can access per month (or yearly or it can be just once with no frequency)

Lightning Platform license don't give permission on case but Salesforce User license does.

Does not include Partner and customer portal licenses

Chatter specific licenses - Chatter External, Chatter Free, and Chatter Only
Chatter only if not available for new agreements. Salesforce suggest to take Lightining Plantform Starter User license.

Community Specific licenses -
1. Customer Community
2. Customer Community Plus
3. Partner Community
4. Lightning External Apps
5. Lightning External Apps Plus

Salesforce license  = all crm functionality including accounts, cases, opps, leads, etc.
Salesforce platform license = all core like account, contact but not cases, leads, etc.

## About IP masking with CIDR notation

Source: https://docs.apigee.com/api-platform/reference/policies/access-control-policy

CIDR notation (Classless Inter-Domain Routing) is a way of indicating a range of IP addresses through masking. It applies to both IPv4 and IPv6. Here's how it works. We'll use IPv4 in our examples for simplicity.

IP addresses are groups of numbers separated by periods. In binary terms, each group is a specific number of bits (8 for IPv4 and 16 for IPv6). The IPv4 address 10.20.30.40 looks like this in binary:

00001010 . 00010100 . 00011110 . 00101000

That's 4 groups of 8 bits, or 32 total bits. With CIDR, you can indicate a range by adding a /number (1-32) to the IP address, like this:

10.20.30.40/16

In this case, the 16 is the number you would use for the mask attribute value in this policy.

This notation means, "Keep the first 16 bits exactly as is, the remaining bits can be anything."

## Knight's tour

Visiting all nodes by making a move of a knight. Special kind of hamiltonion cycle

## Ore's theorem

Sufficiently large graphs are hamiltonion

## greedy algorithm

Try to solve a sub problem at individual step and this will solve the whole problem

## Bézout's identity

if GDC(a,b) = d then there exits X and Y such that aX + bY = d


## Chinese remainder theorem

If one knows the remainders of the Euclidean division of an integer n by several integers, then one can determine uniquely the remainder of the division of n by the product of these integers, under the condition that the divisors are pairwise coprime.

## Euclidean algorithm

Find GDC of 102 and 38

GCD(a,b) = GCD(b, a-b) or faster will be following => GCD(b, a%b)

1. 102 % 38 = 26 => problem is reduced to finding GDC(26,38)
2.  38 % 26 = 12
3.  26 % 12 = 2
4.  12 %  2 = 0

Hence 2 is the GDC

## Extended Euclidean algorithm

Working the Euclidean algorithm backwords to get the X and Y in:

aX + bY = GCD(a,b)

This is imp as this can be used to get mod inverse of a number if a and b are coprime i.e. GCD(a,b) = 1
## constructive proof

Where while prooving you also calculate the answer

## finding inverse of mod - a ^ (-1) mod N

1. Simplest way - try all numbers (let b) from 1 to N so that a*b mod N = 1

2. Efficient way - Using extended Euclidean algo to calculate inverse

3. Euler Totient - applicable only on specific condition

## Sieve of Eratosthenes

Write all numbers and mark all which are divisible by multiples of 2. Then pick next and do the same.

## Segmented Sieve

If the N is large then solving them usig sieve of Eratosthenes will be space consuming. So we break the range in smaller ranges or
length sqroot of N and then solve each.

## Fermat's little theorem

if p is prime then:

a^p is a mod p or a^p - a is a multiple of p or a^(p-1) is 1 mod p

## Fermat primality test

probalistic using fermat's little theorum for multiple as. Try using a few different 'a's which satisfy the equality. If they do then probablity is high that it is a prime. There are 'a's which do satisfy this test.

## Euler's totient function (Euler's phi function)

Number of integers less than 'n' which are relative prime to 'n'

It is multiplicative

## Bijection

Exactly one to one mapping between two sets.

## Lucas theorem

## Miller–Rabin Primality Test

## Reimann Hypothesis & Extended RH

## Ring Theory

Study of rings in which addition and multiplication are defined and have similar properties to those operations defined for the integers

## Abelian group or commutative ring

Set A => take two elements a & b => define an operation (let it be denoted by a dot) => Following should hold

1. Closure - a.b should be in A
2. Associativity - a.(b.c) = (a.b).c
3. Identity element should be in A. Identity element e => a.e = e.a = a
4. Inverse element in A. Inverse = b => a.b = b.a = e
5. Commutative => a.b = b.a

## Noncommutative ring or non-abelian group

when group is not commutative.

## Homology

Mapping abelian groups with topological surfaces.

## Bézout's identity

ax + by = gcd(a,b)

proof => gcd divides both a and b => ax + by is divisible by gcd => ax+by = k*GCD(a,b)


## Greedy algorithm

For some problems, making an optimal choice at every step might result in overall optimal choice. Not every problem can be solved greedily. They are more efficient than dynamic programming


## Spanning tree

A sub graph with minimum edges but all vertices. It has V-1 edges.

## MST - Minimum Spanning Tree

This concept is in case of weighted graphs. This is the spanning tree with least sum of all weights of its edges.

## Dynamic programming

Solving problems iteratively rather than recursively. we can use tabulation (solving sub problems first - bottom up) or memoization (top down - storing solved problems in memory to be reused)

If a problem has optimal substructure then break it down and solve all sub problems. Store (memoize) the solution of the sub problems and use them through lookup when needed. It takes into account all subproblems before arriving at result while greedy method is assuming each step is linearly taking it closer to the final result. Check knapsack problem.

E.g. find min number of coins whose value = X. There are plenty of each coin. Let the value of coins be 1,3,5,10.

1. First you find this for value = 0
2. Then find this for 1
3. Then for 2
4. Then for 3, etc.
5. Keep updating at each step the optimal value. This can be used in the next step.

Take another example of fibonacci calculation. Draw the graph of calculations and you will see some fib(n) multiple times. Dynamic programming will just store those and reuse than to calculate them again.

It is still brute force but in a intelligent way you are trying to reduce it from exponential to polynomial.

It needs two conditions - optimal substructure and overlapping subproblems.

Optimal substructure - Let us take shortest path in a graph as a problem. If a > b has the shortest path p then any node 'n' on the path will have this property - shortest path from a > n is part of path p.

overlapping subproblem - This can be taken care of by memoization. If overlap is not there then it is more like divide and conquer.

## Topological sort (Subproblem dependency DAG (Directed Acyclic Graph) )

Figuring out order of subproblem dependency. E.g. in fibonacci we know that to calculate F(n) calculate f(n-1) and f(n-2) first. So it is a simple order but it might not be always the case.

## Memoization is an issue in cyclic graphs


## Backtracking


## Brute-force

## Self balancing trees (are mainly binary tree - each node can have at most 2 children) Also called sorted or ordered tree

AVL & Red Black are most common - As the elements are deleted or added, the tree rebalances it self to keep the height minimum. These trees help in binary search of elements which is faster.

Property => left child > parent node > right child

## Theta of n

Asymptotically equal. Same order is both lower as well as upper bound. No big or small.

## Big O

Asymptotically less than or equal to. Small o is "less than"

## Big Omega

Asymptotically greater than or equal to. Small omega is "greater than"

## T(N)

is used to demonstrate the amount of work needed to be done for calculating function for n

## N vs NP

N = Problems which can be solved in polynomial time. Also, given the solution, we can see if its correct or wrong in polynomial time.

NP = Solution can be checked in polynomial.

It is called Nondeterministic Polynomial. Which means we can only find non deterministic solutions of order of polynomial.

NP Complete = Is a special class of NP problems which can all be converted to each other in polynomial time. They belong to NP class.

NP Hard = If it is NP Complete but not NP.

## Random Access Machine

A machine which works on the basis of a giant table of indexes of stored words.

e.g. Arrays in C language - a[]

## Pointer Machine

A machine which works on the basis of pointers to indexes. So you go from one word to another but not randomly jump.

e.g. Object access in java - account.contact.Name

## replace \r in files on mac osx

tr -d '\r' < inputfile > output file

## Using sed (Stream editor) commands - does not work on characters like \r which are not identified in macosx. Though they can be worked by some tricks but why use tricks when you have tr command (above)

Normally
sed -i 's/tobereplaced/replacedwith/g' filename

On Mac
sed -i '.bak' 's/tobereplaced/replacedwith/g' filename

-i = in place changes (make changes in original file)
s = replace
g = globally and not just the first occurrence

## How DNS works

Browser Cache > DNS Server configured in the browser (also called recursive DNS) > Root DNS > TLS (Top Level Server) one per com, org, etc. > Authoritative DNS Servers e.g. Amazon/godaddy/etc. > finally the IP for the domain.

## Abstraction

Similar to generalization where we take a complex idea and capture essential details from it so that it can be looked at in a summary. Mostly this abstract model will not just be specific to one idea but to a category of similar ideas. It is like F=MA in physics instead of having different equations for different objects and different slopes. To get generic summary from complex ideas and the slicing and dicing those limited ideas to get all possible specific ideas rather than each complex idea having its own model. Studying in such a way won't lead us anywhere as for every new complex idea we will have to work again rather than using analysis of previously solved cases.

E.g. converting Konigsberg Bridge problem to a graph or converting the social network to a graph. Taking out irrelevant details and reducing it to only the details which we need.

Power of abstraction - Imagine if there were different laws of motion for different objects in different gravitational fields and air friction. So if you change any factor like size, shape or weight of a object or gravitational field or friction, the laws change. Such laws have nearly zero power and use compared to those laws which are more generic. Instead now imagine just 3 laws to define all - law of motion + laws of friction + laws of gravity. Now using these 3 laws you don't need to know a system in advance in order to predict its behavior. You just say, bring it on as you hold these generic laws. That is the magic which people at the time when Newton proposed universal theory of gravity might have felt. The law which governs objects like Moon and sun also govern the falling apple. Such abstraction has two power - Being more generic, it is more useful and also it explains something basic about how a system works. It tells something about the intrinsic nature of such systems. The same applies to computer science concepts.

## SQL Injection

1. Look for places where the data might not be sanitized. You just need to find one such place.

2. Try to input value in form to get the database name. For that there are two important things - number of columns must match if trying UNON (you can add select 1,2, <whatyouwant> from ...) and then try moving the <whatyouwant> based on output. If the output was 2 then put it at the second place for example.

3. Then try to find table name

4. Then find the column names

5. To get more column values if the output is only one column - Use concat function.

## Imperative vs Declarative

Imperative = how
Declarative = what

----
cmd + shift + home = opens home folder in mac

## Naming convention of classes/methods/variables

Both too long and too short are confusing. The name is a valuable real state and should be treated properly.

## AWS DynamoDB

It is a B Tree - Most of the processing (sorting, aggregate filter) is done on application layer rather than DB side. It returns either a single record or contiguous range of data.

Issues with it:

1. Query processing - To get sum of all orders for a customer you need to get all orders and then do the sum in code which might be slow.
2. Cost - Consider the on-demand vs provisioned capacity (which requres reqs are evenly distributed and deciding upfront on the number of requests. If req increases then they will be throttled over the limit)

Note - on-demand is not exactly on-demand. Behind the scenes AWS adjusts limits based on usage and is a opaque process. For peace of mind for big fluctuations, it might be better to go for provisioned.

## AWS S3

Mainly a Hashtable. It is the cheapest storage option available in cloud. Key + Max 5TB blob data as value. Cannot change value. will have to insert a new record and delete the old one. One option for fast changing value is to buffer it in application layer or store it in queue until ready for final save.

Bucket names are globally unique so a good practice might be to start the name with your aws acc id. But still need to check if you own it before pushing or pulling data from there using below code.

s3 = Aws::S3::Resource.new(region: 'us-west-2')
bucket_exists = s3.bucket('my-bucket').exists?

## AWS lambda

Best use case is to use it like a plugin of available services and not as a extension of an application. e.g. generting PDFs from text or docs.

issues - cold start and code limit 250MB. It is stateless so if you want to maintain state while processing then need to use s3 or DynamoDB which can be expensive reads/writes.

## AWS ELB

1. Classic - remains only as a legacy option for EC2s running outside VPC
2. ALB (application load balancers)- Act as Reverse proxy for your servers and can do a lot more like run lambdas, check sessions, etc.
3. NLB (network load balancers) - not proxy but a more of sophisticated network router. More like client directly talking to server.

NLB are faster than ALB as they miss the proxy feature. NLB scale faster than ALB.

ALB are like single tenant and hence scales up or down based on your load and how it scales is opaque to us. Raising a support ticket to raise the capacity is one option if we know we need more.

NLB are like multi-tenant and hence it scales in aggregate so it never fails.

ALB can support multiple domains while NLB can't .

## Route 53 - DNS Service

Nothing special here. Just one limitation that alias is only possible for AWS urls.

## Cloud Formation

Infra as a code. Not everthing should be scripted as it can cause issues. So few things can be manual while things which rarely change should be scripted. Main pupose of this combination is to correctly able to bring down and then up your stack.

## AWS SQS

A normal queue. The best thing is no management is required as there is no kind of limit on this.

Issues - as SQS is multiple queues behind the scene, when you push it goes to a random queue and when you pull it comes from another random queue. So there can be duplicates and no strict ordering. So the application should be able to handle this.

If we need strict ordering and no duplicates then there is a option to select FIFO in SQS but then a limit is imposed on number of requested per sec to 300.

Only one consumer possible and as soon as it is read, it is deleted.

## AWS Kinesis

Similar to SQS but it is a linked list instead of queue.

Multiple consumers possible each maintaining their own cursor. The record is not deleted.
