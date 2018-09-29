---
layout: default
---
# Cryptography Basics

## Digital signature

 What is it and how does it work?

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

Origin > Ceasar > Poly > One time pad

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
---------
Symetric Cipher defined over K(key), M(Message), C(Cypher) is a pair of efficient algo E(Encryption) and D(Decryption) such that:

E:KxM -> C
D:KxC -> M

E is often randomized while D is Deterministic
-------
One Time Pad - Key is of same length as that of message. The cypher is also of the same length

Simple example:
C = E(K,M) = K XOR M

It works because D(E(K,M)) = M

Shannon's Theorem - A cypher has perfect secrecy if cypher reveals no info about message. Following is the mathematical definition
Pr[E(k,m0) = c] = Pr[E(k,m1) = c] This means that based on message m the probability of original message being m0 or m1 should exactly be the same.
No cypher text only attack possible on such algorithms

OTP has perfect Secrecy
Proof
Pr(E(k,m) = c) = 1/|U| - this is because given k & m only one c is possible or rather given c and k only one message is possible.

But issue with OTP is that the key size is same as message. So why not send the message the same way you are sending the key?

Shannon proved that for the perfect secrecy the length of the key should be greater than or equal to the message length. (The number of keys should be equal to or more than the number of possible messages)

##Stream cipher - Are encrypting bit by bit

Instead of using a long length key for OTP. Use a PRG (Pseudo random generator) which takes a seed of length s and generate long key of length n. This function should be efficient and deterministic. The output should look random (defined later).

stream cipher does not have perfect secrecy as the original seed is shorter than the message. But it is secure.

It is unpredictable which makes it secure - Given first i bits of the the cipher nobody should be able to calculate the other bits. The hacker can get the first i bits by knowing that the message starts with a specific prefix (e.g. HEADER or a COLON). More strictly, if given first i bits of the output of PRG it is able to predict with 0.5 + e certainty the next bit. Please note that e is added because anyone can predit the next but with 0.5 prob (consider tossing a coin).

Pracitcal e - generally is considered safe for 1/2^30 because it means that this will happen after 1GB of data.
Theoritically e - e(lambda) < 1/lambda ^ d. e.g. 1/2^lambda is negligible for all lambda

Issues with MS PPNT & 802.11b WEP is that the key gets repeated after 60million frames and is the same once you restart the router. IN WEP though the keys change but they are closely related as every time it is incremented by 1. In 2001 it was showed that it is possible to recover the key after about a million message exchanges.

Using same pad twice is not secure. E.g. in disk encryption.

OTP provides confidentiality but not integrity or non-malleability. E.g. m xor k is modified by attacker by xoring the result with p. The server will decrypt it as m xor p.

Modern Stream ciphers use the concept of nonce (a non repeating long number). PRG takes the seed and a nonce to create a long key. e.g. eStream & Salsa - (k,r) is used only once. So the nonce can change but seed can remain the same.

Its not possible to show if a PRG is secure but it can be statistically proved.


Never use weak PRGs e.g. Linear Congruent Generator - r[i] = a*r[i-1] + b MOD p. Output few bits of r[i].

Semantic Security

Two messages m0 and m1 are encrypted to e0 and e1. The adversary should not be able to guess more than 50% about mapping of e0 and e1 with m0 and m1. The difference between the probability is the advantage (0 means he can't guess anything and 1 means he can guess 100%). Something is semantically secure if the adversary is unable to efficiently have negligible advantage.

Advantage = |Pr(Event A is 1) - Pr(Event B is 1)|

#Block Cypher
n bit input to exactly n bit of Output

Build iteratively

Take a Key > produce multiple keys from that > apply a round function to first key and message > apply a round function to second key and message from previous step > Keep doing this till the end. This applying of the keys again and again is called rounding. Fiestel networks are important here.

Pseudo random function    - F:K x X -> Y This function should be efficient
Pseudo random Permutation - F:K x X -> X This function should be efficient; One to one mapping given a key; efficient inverse algo should exist.

For the PRF to be secure the output should be random for all values of x

DES is based on Fiestel network. Using it we can easily create a inverse function from aribtrary set of function. Fiestel helps in hardware design as the inverse can use the same network.

=========================

Modular Maths - Congruence - How we cut up slices = Equivalence Relation & Slices = Equivalence Class

E.g. Congruence MOdulo C is a Equivalence Relation because it partitions the Integers into different Equivalent Classes

Equivalence Relations have the following property:

1. Reflexive
2. Symmetric
3. Transitive

Quotient Remainder Theorem - Given integers A & B there exit unique integer Q & R such that A = B*Q + R

Addition & Subtraction - (A+B)Mod C = (A Mod C + B Mod C)Mod C

Multiplication - (A*B)Mod C = (A Mod C * B Mod C) Mod C

Exponentiation - (A^B) Mod C = ((A Mod C)^B) Mod C

Inverse - (A*A^-1) Mod C = 1 - A should be coprime to C else inverse does not exist. Can be found manually by trying all possibilities from 0 to C-1

Euclidean Algo help the above calculation

Concept of witness

Passwords are stored using one way function (secure hash). You can only go in one direction and not the other. This is unlike RSA which does provide a trapdoor for the other way. Adding salt helps (e.g.salt = username will make the password = password + username) Salt avoids rainbow attacks

Padding in RSA helps. Read more
================================

```java
//Something
/*sometjng*/

//Comments - #008200 !important
//keywords - #006699 !important
//strings - blue !important
//gray !important

global class CatalogSharingBatch implements Database.Batchable<sObject> {

    global Database.QueryLocator start(Database.BatchableContext BC) {

        String query = 'SELECT Id FROM Contact WHERE Catalog_Sharing_Completed__c = false';

        if(Test.isRunningTest()) {
            query += ' LIMIT 1';
        }

        return Database.getQueryLocator(query);
    }

    global void execute(Database.BatchableContext BC, List<sObject> scope) {

        Set<Id> contactIds = new Set<Id>();
        Map<Id, Contact> contactMap = new Map<Id, Contact>();
        List<Contact> contactsToBeUpdated = new List<Contact>();

        for (Contact cont : (List<Contact>)scope) {
            contactIds.add(cont.Id);
            contactMap.put(cont.Id, cont);
        }

        Map<Id, User> userMap = new Map<Id, User>([SELECT Id, ContactId FROM User WHERE isActive= true AND ContactId IN : contactIds]);

        ParticipantCatalogSharingManager.performSharingOnUserCreation(userMap.keySet());

        for(User u : userMap.values()) {
            contactMap.get(u.ContactId).Catalog_Sharing_Completed__c = true;
            contactsToBeUpdated.add(contactMap.get(u.ContactId));
        }

        update contactsToBeUpdated;
    }

    global void finish(Database.BatchableContext BC){}
}
```
