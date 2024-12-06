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

## what are spring projects? 
these are additional modules built on the existing spring framework. 
![[Pasted image 20241206142542.png]]
only use the modules that you need currently. 
visit www.spring.io for more details

# Maven? 
its a project management tool for your application. 
it is used for build management and dependencies. 
without maven: download the jar files from each project web site. manually add the jar files to your build path each time. maven does all that by itself saving a lot of time for the developer. 
![[Pasted image 20241206143017.png]]
maven will take care of all these jar files by itself. developer can focus on actual development tasks. 
- as said earlier, maven is your personal shopper. 
![[Pasted image 20241206143147.png]]

![[Pasted image 20241206143222.png]]
other tasks of maven:
- each dev team decides its own project structure accordingly. this can be difficult for new comers. 
- maven solves this problem by providing a standard directory structure. 
- so inshort maven has a way of project directory designing. 
- 5 important files and folders in a maven project are: 
	- pom.xml 
	- src
		- main
		- test
	- target: destination directory for compiled code. 
- maven handles configuration like a pro in a new machine for an existing maven project. 
- pom.xml file: 
	- project object model file. shopping olist for maven which tells maven what dependencies to include. it has project metadata, dependencies, and plugins. 


## Springboot starters: 
this is a list of maven dependencies grouped together and tested by the spring development team. this starters make it much easier for the develoer to get started with spring 
examples below: 
- **Core Starters:**
    
    - `spring-boot-starter`: Basic starter for core Spring Boot functionality.
    - `spring-boot-starter-web`: Starter for building web applications, including RESTful services.
    - `spring-boot-starter-data-jpa`: Starter for Spring Data JPA with Hibernate.
    - `spring-boot-starter-security`: Starter for adding Spring Security.
- **Specialized Starters:**
    
    - `spring-boot-starter-thymeleaf`: Starter for using the Thymeleaf template engine.
    - `spring-boot-starter-test`: Starter for testing libraries like JUnit and Mockito.
    - `spring-boot-starter-logging`: Starter for logging with Logback and SLF4J.
- **Messaging and Integration Starters:**
    
    - `spring-boot-starter-redis`: Starter for using Redis.
    - `spring-boot-starter-amqp`: Starter for using RabbitMQ.
- **Cloud and Microservices Starters:**
    
    - `spring-cloud-starter-netflix-eureka-client`: Starter for Netflix Eureka client.
    - `spring-cloud-starter-zipkin`: Starter for distributed tracing with Zipkin.

# running the application from command line 
- since the springboot app has embedded server, there is no need to separately start a server and then run the application. 
- use "java -jar mycoolapp.jar" in the appropriate directory
	- - Build the JAR file using Maven:
	    `mvn clean package`
	- Navigate to the target directory (or wherever the JAR file is located):
	    `cd target`
	- Run the application:
	    `java -jar mycoolapp.jar`
- using maven: go to the project directory where pom.xml is located.
	- **For Development:*
    - Use:        
        `./mvnw spring-boot:run`
	    - This skips the packaging step and directly runs the application.
- **For Deployment:**
    - Build the JAR file:
        `mvn clean package`
    - Run the application:
        `java -jar target/mycoolapp.jar`


# Injecting custom application properties
- by default, spring boot reads information from a standard properties file which is application.properties. 
- we can define any custom properties in this file. the spring boot app can access properties using @Value annotation. 
