---
layout: default
---
# Mathematics

## Group Theory -
Commutative / Abelian group

## Types of numbers:

1. Real
2. Complex
3. Rational
4. Irrational
5. Algebraic (root of a polynomial)
6. Transcendental (Which are not algebraic)

## Countable Infinity
Mainly should be able to go one by one through the set so that there is an order in which you are not skipping anything or counting something twice. Mainly that you are able to associate an integer to each member of the set.

## fundamental theorem of algebra
Any polynomial with single variable and complex coefficient will have at least one complex root. 

## Chaos Theory
3 body motion - Henri Poincare - initial conditions made lot of changes in the system.

## History of logic

Started with Arestotlian logic - Close to propositional logic
George Bool then refined it and was poslished and made famous by Bertrand Russell


## Propositional Logic

Deals with relationship between propositions as a whole

relationships (Connectives)- conjunction (AND), disjunction (OR), conditional (If Then), negation (Not)

\\(\tilde\\) - negation
. - conjunction
\\(\tilde\\) - disjunction
\\(\nsubseteq\\) - if then, only if
\\(\equiv\\) - equivalence


Basic unit is declarative statement (and not individual pieces) which cannot be true or false (truth value)
E.g.
John = subject => cannot be true or false
wearing a coat = predicate => cannot be true or false

So the above by themselves are not statement but when they are joined they become a statement
John is wearing a coat

Define statement > Statement can be true or false
Cannot deal with questions or imperatives as they can't be true or false

Propositions = are denoted with upper case letters

connectives = negation, or, and and if then.

## Predicate logic

Somethings cannot be learnt just by using Propositional logics. E.g.

P = All men are mortal
Q = Socrates is a man
R = Socrates is mortal

Using propositional logic we can not get R from P & Q. So we use predicate logic. Predicate is a property of an object.

Components of predicate logic:

1. Predicates
2. Terms - Constants and variables
3. Connectives - same as from propositional logic
4. Quantifiers: Universal - \\(\forall\\), Existential - \\(\exists\\)

e.g. how to write - All men like cake and pie

- Mx = x is a man
- Lxy = x likes y
- c = cake
- p = pie

(\\(\forall\\) x) (Mx -> (Lxc ^ Lxp))

e.g. how to write - Some men like cake and pie

- Mx = x is a man
- Lxy = x likes y
- c = cake
- p = pie

(\\(\exists\\) x) (Mx ^ (Lxc ^ Lxp))

Use -> for Universal Quantifiers and ^ for Existential

## Branches of Mathematics

1. Computational Geometry - When any problem including algorithmic problems can be expressed in as a geometrical problem.

2.

## Important Theorem for Cryptography:

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
