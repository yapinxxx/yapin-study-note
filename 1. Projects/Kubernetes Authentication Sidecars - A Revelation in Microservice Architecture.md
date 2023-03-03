---
date: 2023-01-16_Mon 10:51
aliases: []
---

# MetaData
Status :: #🌱<br>
Note Type :: #📝<br>
Source URL :: [Kubernetes Authentication Sidecars - A Revelation in Microservice Architecture](https://betterprogramming.pub/kubernetes-authentication-sidecars-a-revelation-in-microservice-architecture-12c4608189ab) <br>
Source Type :: #onlineArticle  <br>
Author :: #MattBentley <br>
Topics :: #Kubernete, #Microservice, #Authentication<br>

---

# Evergreen Note
Question :: What is this article talking about? <br>
-> <br>
Answer :: About Authentication <br>

---

# Summary

---

# Note

> A history of authentication and how to solve authentication in a reusable way using sidecar containers in [[Kubernetes]]

![[Pasted image 20230116104031.png]]

# Kubernetes Authentication Sidecars - A Revelation in Microservice Architecture

## History

### Cookie authentication

Cookies have been used to authenticate front-end applications for a while, but traditionally they have had some downsides:
- CSRF attacks
- Session cookies

### JWT authentication

Along came JSON Web Tokens, which helped us solve some of these drawbacks with cookies by providing self-validating stateless tokens. JWTs can be decoded to retrieve a user’s claims and validated on any server using a public key.

For these reasons, over recent years, JWTs have been pushed by promoters as the holy grail of authentication… Unfortunately, our tale does not end there! There are some key disadvantages to using JWTs that people often overlook or do not understand (There’s a great article explaining [here](https://redis.com/blog/json-web-tokens-jwt-are-dangerous-for-user-sessions/) if you’d like to know more):
- Revocation
- XSS Attacks

### Web Security to the Rescue!
Luckily over time, a lot of the issues with cookies and JWTs have been prevented with security features:
- 'SameSite' cookie policy
- 'HttpOnly' cookie
- Data Protection Keys
- CORS and CSPs


### JWTs are Dead; Long Live the Cookie!

### Self Authentication Approach

### Sidecar Authentication Approach

### Benefits of sidecar authentication

### Forwarded claims and headers

---

## ASP.NET YARP Implementation

### Authentication

### Authentication scheme detection

### Authorization

## YARP Configuration

## Kubernetes Deployment

### Sample application architecture
### Kubernetes manifests


