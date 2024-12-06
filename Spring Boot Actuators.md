**Spring Boot Actuator** is a module in Spring Boot that provides built-in production-ready features to help you monitor and manage your Spring Boot application. It exposes a wide range of useful endpoints that allow you to interact with and inspect the health, metrics, environment, and other aspects of your application.

**think of actuators as a dev tool which gives information about current status of the application to the dev**

simply add the dependency to your pom file. the rest endpoints are automaticallyadded to your application. 

some endpoints of the actuators are:
/actuator/health: this gives health information about your application. this is normally used for checking if the application is up or not. 

/info end point can provide information about the application. we have to update application.properties with your app info for the info to show. 
another is /cache: this shows cache currently in session. 

by default only /health is exposed. 

## question: what about the security of the application data? a general user would be able to see critical performance data of the application? 
for disabling actuator endpoints in the final build, we use spring security: 
1. go to the pom file and add dependency spring-boot-starter-security
2. now when you access /actuator/beans, spring security will prompt for login. only when the login process is complete, then you will be able to see the beans data. 
3. default user name is: user and default password comes in the compiler. 
4. we can set custom username and password. 
5. with spring security, we can actually customize spring security for spring boot actuators and use a database for roles, encrypted passwords, etc. 
