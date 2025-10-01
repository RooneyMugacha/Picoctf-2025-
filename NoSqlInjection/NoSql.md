The followin ctf test on NoSql injection(NoSQL injection is a vulnerability that allows an attacker to manipulate or bypass NoSQL database queries 
by injecting malicious input into an application.
The document source file has a file called Server.js
In this file we can see than we use MongoDb for our Database, and password and email required to have "{"
  email.startsWith("{") && email.endsWith("}")
              ? JSON.parse(email)
researching on MongoDb NoSql vulnerability we come across {"$ne":null}
we input it into our login page .Using Burp suite to intercept while login in
we find a encoded token which when Decoded gives out the flag.
