# why springboot: 
- traditional spring framework development was hard with manual configuration. 
springboot helps in dependency conflicts. 
- it provides an embedded http server so you can get started quickly. (eg tomcat, jetty).

## springboot uses spring behind the scene 
both are of same speed during runtime due to being the same in the workings inside. 
springboot makes it easier to use spring, that's it. 

# starting up... 
- spring initialiser website is used for creating a spring boot project. 
- we can select dependencies, built tools etc in the initializer accordingly. 
- intellij, NetBeans, eclipse can be used. 

# what about server?:
- spring boot provides an embedded http server like tomcat. 
- the jar file which has our application code ef app.jar has 2 things -the source code and the server included. 
- springboot apps can be a standalone project since it includes the server itself in the jar file. 

# deployment: 
- speingboot applications can be deployed in the traditional way. deploy a war file to external server and it will work just fine like any other piece of code. 
 
# maven:
- popular built tool which helps programmer to download and install dependencies. user tells maven what dependencies to download and maven will go and download them from their repository or cdn and install it without user having to go to each single site and installing it. 
- think of maven as your personal shopper who you give a shopping list to. 

# Spring initializr
- select project built tool - maven
- select language - java
- select spring boot version - lts version selected by default, dont select snapshot versions since they are in beta testing. 
- add dependencies as needed. 
- select jar packaging for springboot java project. 
- select java version available in dev machine. 

