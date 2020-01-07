---
layout: default
---
# Mathematics

Types of numbers:

1. Real
2. Complex
3. Rational
4. Irrational
5. Algebraic (root of a polynomial)
6. Transcendental (Which are not algebraic)

Important Theorem for Cryptography:

1. Chinese Remainder Theorem
2. Fermat's Little Theorem
3. AKS
4. Theorems on Perfect Number

Commutative - Order when applying the operator does not matter: AxB = BxA
Associative - Sequence of execution of operator does not matter: Ax(BxC) =(AxB)xC


Fermat's little Theorem
-----------------------
Although Fermat said that is it true only for prime numbers, it not not correct. It is true for pseudoprime numbers which pass the test but are composite.
Testing for many value of 1 < a < p-1 helps establish more chances of it being a prime. However there is a special kind of pseudoprime called Carmichael number. This class of number passes all test for all a. So that is the problem with this test. Many a times the pseudoprime from this Theorem are simply called pseudoprime instead of adding the modifier of Fermat.

Gauss formulaized modular operations in 1800

congruences can be multiplied and added like ordinary maths but inverse is very different. For the same reason you can't cancel numbers on the two sides like ordinary maths

(You can only cancel the number k when it is coprime to N from Mod N or GCD(k,N) = 1)
If the above is true then k.k' is congruent to 1 Mod N

GCD(k,N) = 1 implies sk + tN = 1 (Reversing steps of Euclidean Algo)

Fermat's primality test - Using fermat's to predict if a number is prime. This is not a great method considering Carmichael numbers

Miller-Rabin primality test - Uses Fermat's little Theorem and the concept of square of 1 under mod N to predict a prime. This is better becasue each iteration has a chance of predicting the prime correctly by 1/4. So each iteration is acutally getting us closer to the solution unlike Fermat's primality test.

AKS Algo - it is the only known polynomial Deterministic algo for primality testing. It is stated as follows:

p should divide all the coefficient in  (X-1)^p - (X^p-1)

---
Gauss found the prime number distribution (n/logn)

Riemann's Zeta function - student of gauss created this. Euler found this too but only for real while riemann found it for complex number. Somehow zeta is closely related prime number.

Diophantine equation - polynomial in 2 or more variables where we are seeking intergal solution

Elliptic Curve - y^2 = x^3 + ax + b - Take two rational points and extend the line both ways. It will intersert the curve again at 3rd point. This will be rational too.
---------

GCD of two numbers is always a linear combination of those two numbers.

a & b can be found using extended Euclid algo

if GCD is 1 then x and y are relatively prime

inverse of a number in mod is (N+1)/2 - inverse is only possible if x and N are relatively prime

Zn is the ring and Zn* is the set of elements which have a inverse

Consistency of public key encryption is D(E(x)) = x
