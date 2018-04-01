---
layout: default
---
# Cryptography Basics

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
Use filters in J2EE for authenticating the users everytime a request is made.

Create a class which implements Filter class. This should have the methods - doFilter, init and destroy.

<filter>
    <filter-name>UserAuthFilter</filter-name>
    <filter-class>com.servlet.filter.UserAuthFilter </filter-class>
    <init-param>
      <param-name>avoid-urls</param-name>
      <param-value>/login.jsp,/static.jsp</param-value>
    </init-param>
  </filter>
  <filter-mapping>
    <filter-name>UserAuthFilter</filter-name>
    <url-pattern>/*</url-pattern>
  </filter-mapping>

---------------------

