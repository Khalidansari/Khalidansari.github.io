---
layout: default
title: Python
---

# Core commands in Python

1. help(componentName) - shows doc string of componentName. Due to its common use, there is a shortcut componentName?

2. componentName?? will show the source code if it is implemented in python

## Quick summary of basic python data science/ML libraries:

https://jakevdp.github.io/PythonDataScienceHandbook/index.html


# Numpy

Mainly ndarray - allocates contiguous memory; can do SIMD operations (same operation on all elements at processor level); as the data type is same in numpy for a given array, it runs faster. Some extra operations are available which are not there in python core e.g. multiplying two arrays to give array with element by element multiplication.

## Regular Operations

2. One dimensional - nd.array([1,2,3])

3. Two dimensional - nd.array([[2,3,4],[5,3,1]])

4. size - arrayName.ndim

5. Shape - arrayName.shape

6. Data Type - arrayName.dtype

7. Forced data type - nd.array([1,2,3], dtype='int16')

8. 1 dimensional matrix with all zeros - np.zeros(5)

9. 2 dimensional martix with all ones - np.ones(2,3)

10. matrix with all having a specific number - np.full( (2,2), 99)

11. How to be sure about indexing in case of traversing a multidimensional array - start from outside brackets

12. 4x2 Matrix of random numbers between 0-1 - np.random.rand(4,2)

13. 3x3 Matrix of random between 4-6 - np.random.randint(4,6,size=(3,3))

14. 5x5 matrix of identity matrix - np.identity(5)

15. Repeat an array to make new array - np.array

16. Create clone of ndarray - arrayName.copy()

17. Element wise operation - a + 2 or a - 2 or a / 4 - Does the operation with all elements and returns the same shape of matrix.

## Linear Algebra

1. AxB (where last dimension of A is first dimension of B) - np.matmul(A,B)

2. Determinent of A - np.linalg.det(A)
