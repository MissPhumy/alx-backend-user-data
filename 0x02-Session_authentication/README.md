# 0x02. Session Authentication

## Background Context
In this project, you will implement a Session Authentication. You are not allowed to install any other module.

In the industry, you should not implement your own Session authentication system and use a module or framework that does it for you (like in Python-Flask: Flask-HTTPAuth). Here, for learning purposes, we will walk through each step of this mechanism to understand it by doing.

## Resources
Read or watch:
- [REST API Authentication Mechanisms](#)
- [HTTP Cookie](#)
- [Flask](#)
- [Flask Cookie](#)

## Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

### General
- What authentication means
- What session authentication means
- What Cookies are
- How to send Cookies
- How to parse Cookies

---

### What authentication means
Authentication is the process of verifying the identity of a user or system. It ensures that the entity trying to gain access is who or what it claims to be.

### What session authentication means
Session authentication is a mechanism where the server creates a session for the user after they log in, storing the session ID in a cookie that is sent to the client. The client sends this cookie with each subsequent request to authenticate the user.

### What Cookies are
Cookies are small pieces of data that are sent from a website and stored on the user's computer by their web browser. They are used to remember information about the user, such as their login status or preferences.

### How to send Cookies
Cookies are sent from the server to the client using the `Set-Cookie` header in the HTTP response. For example:
