---
layout: default
---
# Quick Notes for Competitive Programming

## Sorting arrays in Java

Array.sort() in Java uses quick sort for sorting primitive data types. In worst case it will take order of $$n^2$$ (which would be when the input array is nearly sorted). However, Java uses merge sort for sorting array of objects. Merge sort takes $$n \log n$$ in worst case. So it is better to convert primitive to object wrapper before sorting. Alternate trick would be to randomize the input of primitive array before sorting so the chances of it being nearly sorted reduces.

\- [Reference from codeforces](https://codeforces.com/blog/entry/7108%3Flocale%3Dru)

## Using large numbers instead of int/Integers