---
layout: default
---
# Cryptography Basics

## Digital signature

## What is it and how does it work?

It works on the principle of asymmetric encryption algoritm. Generally all the algorithms we think of intutively when encrypting is symmetric. When we were in school we could exchange encrypted messages by simply rotating alphabets - e.g. replace A with C; B with D; C with E and ... Z with B. But what if someone comes to know how we are encrypting? If they know that we are simply rotating/moving an alphabet two places higher than they can decrypt it by moving each alphabet in encrypted text by moving them two places lower (moving C to A, etc.). Hence in symmetric encryption algorithms knowing the encrption key (the method/way encrption is done) jeopardizes everything.

A digital signature is used to verify a message. It is basically an encrypted hash (encrypted by the private key of the sender) of the message. The recipient can check if the message was tampered with by hashing the received message and comparing this value with the decrypted signature. To decrypt the signature, the corresponding public key is required.

A digital certificate is used to bind public keys to persons or other entities. If there were no certificates, the signature could be easily be forged, as the recipient could not check if the public key belongs to the sender. The certificate itself is signed by a trusted third party, a Certificate Authority like VeriSign.

Other points:

I. Encrypt passwords using one-way techniques, this is, digests.

II. Match input and stored passwords by comparing digests, not unencrypted strings.

III. Use a salt containing at least 8 random bytes, and attach these random bytes, undigested, to the result.

IV. Iterate the hash function at least 1,000 times.

V. Prior to digesting, perform string-to-byte sequence translation using a fixed encoding, preferably UTF-8.

VI. Finally, apply BASE64 encoding and store the digest as an US-ASCII character string.
---------------------
Ready made java api - jasypt
--------------------
MD5 is of not much use because it does not use salt.
--------------------
##Term

E - Encrption Algo
D - Decreption Algo
M - Message space
C - Cypher Text
K - Key Space

##Perfect Secrecy

For any given c, the following should hold for all messages in M:

Probability of m0 being original text is same as m1 being original text. This boils down that the probability should be constant.

Bad new lemma - Perfect Secrecy is only possible if the length of c is same or more than the length of m.

## How to make it efficient?

As noted above, it is not useful to have perfect secrecy as it will demand long key length

This requires the concept of Pseudo-Random-Generator

G : {0,1}^s -> {0,1}^n

n should be very large than s and the result should look random.

-----------
Terminology

Universe (U) - Set of elements - Generally, it contains all the possible binary numbers constraint by a particular length of the number - e.g. {0,1}^n

Probability Distribution (P) over Universe (U) is a function P: U -> [0,1]

1. Uniform Distribution - for all xEU P(x) = 1/|U|

2. Point Distribution at X0 - P(x0) = 1 and for all other points it is 0

Distribution Vector - (P(1st element in U), P(2nd element in U)... P(last element in U))

Event (A) - Subset of U - P(A) = Summation of P(x) over all xEA

Pr(AUB) <= Pr(A) + Pr(B) {The difference is of Pr(AnB)}

Random Variable (X) - Is a function over U - X:U -> V

Uniform Random Variable (r) - represented as "r <- over R - U" - For any element a of U the following should hold Pr(r=a) = 1/|U|

r is a identify function??

Deterministic algorithms - y <- A(m)

Randomized algorithms - They additionally take a random variable to generate a random output.

y <- A(m;r) where r <- R - U

implies the following

y <- R - A(m)

Independent events A & B implies Pr(A and B) = Pr(A).Pr(B)

Two random variable X & Y are independent iff - for all elements in U Pr(X=a and Y=b) = Pr(X=a).Pr(Y=b)

XOR of two strings = bitwise addition mod 2

If Y is a random variable and X an independent uniform variable then Z:= Y XOR X is uniform Variable

Birthday Paradox - Let r1, r2, r3, ... E U be independent random variables. When n = 1.2*Sqrt(|U|) the probability that two rs are same is > 0.5

This is called collision probability. It converges very fast. E.g. for 1000 it can be 0.5 and for 3000 it can be 0.99
