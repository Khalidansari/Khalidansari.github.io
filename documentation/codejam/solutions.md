---
layout: default
---
# Unix

Single Sign On

OAuth2 is an authorization protocol that doesn’t define the specifics of how the authentication occurs, but any complete implementation will support a variety of authentication mechanisms. These grants include:

* Authorization Code Grant
* Implicit Grant
* Resource Owner Password Credential Grant 
* Client Credential Grant

The OIDC spec adds to this list by providing a set of authentication flows including:

* Authorization Code Flow
* Implicit Flow
* Hybrid Flow

Message Digest (MD) = Hash

Digitally Signing something = Message > Hash > Encrypt with private key > send > received by receiver > Decrypted using public key > check if message was tampered with (Message and its encrypted hash (digital sig) was sent together. The receiver will separate them and compare the signature after decrypting it and hash of the message.

JWT Token - > digitally signing the ids - used if certificates are to be used. For server to server connection. https://en.wikipedia.org/wiki/JSON_Web_Token

Single Signon - SAML, OpenID Connect
API Access - OAuth & OpenID Connect
Server to Server - JWT Tokens

JIT Provisioning - create users on the fly in Salesforce. Option available only through SAML. The new user attributes can be passed in the SAML assertion. Need to provide prefix of object name to the field to specify the object as well. e.g. User.Username. ProfileId field can be name or Id.

JIT For Communities > Find match using fed id > find match using contact details > find match using account > else create account and others

SAML Bearer flow in OAuth is same as Authorization Code flow except that a refresh token is not issued. A SAML Assertion token is sent in the request and a certificate is uploaded in salesforce.
