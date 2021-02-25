---
layout: default
title: Python
---

# Core commands in Python

1. help(componentName) - shows doc string of componentName. Due to its common use, there is a shortcut componentName?

2. componentName?? will show the source code if it is implemented in python

3. get ascii for a char => ord(char) and it is not int(char)

4. Get char from ascii? chr(int)

5. binary to int - int('11111111', 2)

6. int to bin - bin(x)

7. difference between x//y and int(x/y) -
e.g. print(-13//5) = -3
print(int(-13/5)) = -2

8. Max can take extra argument as key using which the elements are compared. This extra argument should be a funciton.
e.g. max(map.keys(), map.get)

9. VSCode tip - comment selected lines > cmd + k + c and uncomment using cmd + k + u

10. In javascript you can access any property even if it exit or not.  This can be avoided by typescript

11. Type script gives ability to give a type "any" to say that don't care about type. When moving fast this might be helpful to act like js.

12. difference between sorted and sort

a. sort does it in place while sorted returns a new list which is sorted.
b. sorted can take other arguments like "reverse" and "key"

sorted(mylist, reverse=True)
sorted(mylist, key=len)

13. all or any

all([num % 2 == 0 for num in [2, 4, 6, 8, 10]])
True
all([num % 2 == 0 for num in [2, 4, 6, 8, 9]])
False

14. chr and ord

chr(165) -> convert unicode into char
ord('a') - convert char into unicode

15. dir(obj)

shows all attributes of an object

16. enumerate - converts list to a list of tuple with index.

input = [a,b,c]
output = [(0,a),(1,b),(2,c)]

17. eval() - anything as a string inside it is executed as a code. Awesome but dangerous.

18. filter - takes two arguments - first is a function which returns boolean and the second one is a list.

def is_even(num):
    if num % 2 == 0:
        return True
    return False
f_even = filter(is_even, [1,2,3,4,5,6,7,8])

## Quick summary of basic python data science/ML libraries:

https://jakevdp.github.io/PythonDataScienceHandbook/index.html

3. In most languages and not just python use the following to get decimal value - 3.1 % 1 = 0.1

4. John Carmack used a workaround to put out a faster implementation of inverse square root using magic number.

5. string.count(pattern) - gives the number of times the pattern appears in string

6. x^y = xor

7. convert int to binary = bin(x) - it will have 0b in the start so to get just the ones and zeros do this - biin(x)[2:]

8. Brian Kernighan's Algorithm - Bit counting algo. Take 11001000010 for example. Either we keep going one by one from left to right in 11 steps or we can use the following trick to jump all continuous zeroes in a single step. Trick is to use x&(x-1) - this will remove the left most one. Keep doing this one by one until the number is 0

  step 1
  11001000010 - x
  11001000001 - x-1
  11001000000 - x&(x-1)

  step 2
  11001000000 - x
  11001111111 - x-1
  11000000000 - x&(x-1)

9. Create empty list - either list comprehension or [None]*size

10. get both index and value in loop - for index,x in enumerate(list)

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

18. When dividing large ints, better to use // instead of / to get int as output. Int is not bounded but float is.

19. sort and sorted functions take optional "reverse=True" - for reverse sorting and "key=function" for custom sorting. function should take one param and return one param - e.g. lambda x: len(x) or lambda x: x % 2

## Linear Algebra

1. AxB (where last dimension of A is first dimension of B) - np.matmul(A,B)

2. Determinent of A - np.linalg.det(A)
