---
layout: default
---
# Quick Notes for Competitive Programming

## Sorting arrays in Java

Array.sort() in Java uses quick sort for sorting primitive data types. In worst case it will take order of $$n^2$$ (which would be when the input array is nearly sorted). However, Java uses merge sort for sorting array of objects. Merge sort takes $$n \log n$$ in worst case. So it is better to convert primitive to object wrapper before sorting. Alternate trick would be to randomize the input of primitive array before sorting so the chances of it being nearly sorted reduces.

\- [Reference from codeforces](https://codeforces.com/blog/entry/7108%3Flocale%3Dru)

## Using large numbers instead of int/Integers

Integers are limited to $$\approx \pm$$ 2 billion and floats are not precise (e.g. 0.4 - 0.3 $$\ne$$ 0.1 in java if using floats) due to their implementations (IEEE 754). Hence using BigInteger and BigDecimal is the right way to go.

# SOLID Principles - given by Robert C Martin

Single-responsibility principle[6]
A class should only have a single responsibility, that is, only changes to one part of the software's specification should be able to affect the specification of the class.
Open–closed principle[7]
"Software entities ... should be open for extension, but closed for modification."
Liskov substitution principle[8]
"Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program." See also design by contract.
Interface segregation principle[9]
"Many client-specific interfaces are better than one general-purpose interface."[4]
Dependency inversion principle[10]
One should "depend upon abstractions, [not] concretions."[4]
