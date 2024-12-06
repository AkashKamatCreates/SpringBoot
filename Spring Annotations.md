## @SpringBootApplication
this signifies that the application is a springboot application. 

``` java 
package com.course.springbootdemo.myappcool;  
import org.springframework.boot.SpringApplication;  
import org.springframework.boot.autoconfigure.SpringBootApplication;  
@SpringBootApplication  
public class MyappcoolApplication {  
    public static void main(String[] args) {  
       SpringApplication.run(MyappcoolApplication.class, args);  
    }  
}
```
## @RestController
sets up the rest controller for the application
## @GetMapping("/")
as the name suggests, getmapping annotation helps us set what to display on what url. 
this getmapping annotation is used to handle http GET request. 

```java
package com.course.springbootdemo.myappcool.rest;  
  
import org.springframework.web.bind.annotation.GetMapping;  
import org.springframework.web.bind.annotation.RestController;  
  
//restcontroller annotation to tell spring to use this class as the rest controller class.  
@RestController  
public class FunRestController {  
    //expose a "/" endpoint that returns hello world.  
    @GetMapping("/")  
    public String sayhello(){  
        return "hello world";  
    }  
}
```

## @Value 
The `@Value` annotation in Spring Boot is used to inject values into fields, method parameters, or constructor arguments. These values can come from:

1. **Application properties or YAML files** (e.g., `application.properties` or `application.yml`).
2. **Environment variables**.
3. **System properties**.
4. **Hardcoded values**.
5. **Default values if the property is not specified**.

in your application.properties:
```properties
#defining name properties  
first.name = akash  
last.name = kamat
```
in the RestController.java:
```java
@Value("${first.name}")  
private String fname;  
  
@Value("${last.name}")  
private String lname;  
  
@GetMapping("/fullname")  
public String fullname(){  
    return "first name = "+fname+" and last name = "+lname;  
}
//output: first name = akash and last name = kamat
```
