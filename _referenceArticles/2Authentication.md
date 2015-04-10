---
title: Introduction
anchor: introduction
---

# Authentication

For simplicity reasons, the authentication will currently be done using HTTP Basic user/pass token that should be communicated with every request, through a HTTPS channel (the app is not available in plain text HTTP).

This token(s) can be renewed/invalidated by the client manually on the appropriate interface.

For all the libraries that only have generated code, the authentication hasn't been implemented. Because of that, we add here the Java code snippet that we currently use to take care of the authentication (which we put here so that it can be used as a 'pseudo code' example for other languages): 


```
 public static void setCredentials(String username, String password) {
        ApiInvoker apiInvoker = ApiInvoker.getInstance();
        String userCredentials = username + ":" + password;
        String basicAuth = "Basic " + new String(Base64.encode(userCredentials.getBytes()));
        apiInvoker.addDefaultHeader("Authorization", basicAuth);
    }
``` 
 
