---
date: 202302141830
aliases: []
---

# Metadata
Status :: #ð± #ð¼ #ð² <br>
Note Type :: #ð #ðºï¸ <br>
Source URL :: []() <br>
Source Type :: #(æ³æ³ãæ¸ç±ãç¶²è·¯æç« ãå½±çãèª²ç¨ãPodcastãPDF/é»å­æ¸ãèå¤©ãè²¼æã)<br>
Author :: #(The Information Author)<br>
Topics :: #(ç´éç­è¨ç¸éçä¸»é¡ (MOC)ï¼ä¸»é¡ (MOC) ä¾æéè¦æä¸æ·æ°å¢ãä¾å¦æéç®¡çãå°æ¡ç®¡çãç¢åç®¡ç...ç­ã) <br>


---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# High-Level overview of use Docker to combine LDAP server, Web Application, Casbin Library
[[Access Control]]

1.  Create Docker containers for each component:
    
    -   For the LDAP server, you can use an existing Docker image for an LDAP server, such as OpenLDAP.
    -   For the web application, you can create a custom Docker image based on your application code and dependencies.
    -   For the Casbin library, you can use a pre-existing Casbin Docker image or build your own based on your needs.
2.  Configure the LDAP server container to store user authentication information, such as usernames and passwords.
    
3.  In the web application container, implement user authentication by integrating with the LDAP server. Store the user's role in the user's session after successful authentication.
    
4.  Implement access control enforcement in the web application by integrating with the Casbin library. Retrieve the user's role from the user's session and use it to determine if the user is allowed to access a protected resource.
    
5.  Define access control policies in a policy file and store it in a location accessible to the web application and Casbin library containers.
    
6.  Connect the containers using Docker's networking features, such as linking or using a shared network.
    
7.  Start the containers and test the system to ensure that user authentication and access control enforcement are working as expected.
    

By using Docker, you can package and deploy the system as a set of containers, making it easier to manage, scale, and deploy in different environments.