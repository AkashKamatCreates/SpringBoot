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

## 
