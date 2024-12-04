1. create a new package called rest. here is where you will store rest controllers of the whole project. 
2. create java class in the package. eg: FunRestController. 
3. next follow the sample code: 
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
