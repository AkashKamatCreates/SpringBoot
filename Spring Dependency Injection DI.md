### **What is Spring Dependency Injection (DI)?**

**Dependency Injection (DI)** is a design pattern where an object's dependencies are supplied (injected) by an external entity rather than the object creating them itself. In Spring, DI is a fundamental feature, and the **Spring IoC (Inversion of Control) container** is responsible for injecting these dependencies.

---

### **Why Dependency Injection?**

1. **Loose Coupling:**
    
    - Classes don’t need to know about the concrete implementation of their dependencies. They rely on abstractions instead.
2. **Reusability:**
    
    - Dependency injection makes components easier to reuse in different contexts.
3. **Testability:**
    
    - Dependencies can be mocked or substituted during testing, making unit tests easier to write.

---

### **Analogy to Explain Dependency Injection**

Think of a car manufacturing plant:

1. **Without DI (Manual Dependency Management):**
    
    - The **engine** factory creates engines and installs them into cars itself.
    - The **tire** factory creates tires and installs them into cars itself.
    - The car assembly plant tightly depends on these factories, making it hard to change or upgrade components.
2. **With DI (Spring's Approach):**
    
    - The **car assembly plant** simply receives engines and tires from external suppliers.
    - It doesn’t worry about how they are manufactured—this responsibility is delegated to the suppliers.

**Spring is like the logistics manager, ensuring all components (dependencies) are delivered to where they are needed (objects).**

# 2 injection types: 
1. constructor injection: use this when you have required dependencies. recommended by the spring.io development team as first choice.
2. setter injection: use this when you have optional dependencies. if dependency is not provided, your app can provide reasonable default logic. 

# What is Spring autowiring: 
- for DI, we can use autowiring. 
- spring will look for a class that matches by type: class or interface. 
- spring will inject it automatically, hence it is autowired. 
### **What is Autowiring in Dependency Injection (DI) in Spring?**
**Autowiring** in Spring is a feature that allows the **Spring IoC container** to automatically resolve and inject dependencies into beans. Instead of explicitly defining dependencies in the configuration, you can use annotations like `@Autowired` to let Spring handle the injection automatically.

---
### **How Does Autowiring Work?**
1. **Spring identifies dependencies** required by a bean (class).
2. It looks for a matching bean in the Spring container (based on type, qualifier, or name).
3. **Spring injects the dependency** into the target bean automatically, without requiring explicit configuration.
---
### **Why Use Autowiring?**
1. **Reduces Boilerplate Code:**
    - Eliminates the need to explicitly wire dependencies in configuration files.
2. **Simplifies Configuration:**
    - Dependencies are automatically resolved, leading to cleaner and more readable code.
3. **Promotes Loose Coupling:**
    - The application components are decoupled because the IoC container handles wiring.
---
### **Types of Autowiring in Spring**
1. **By Type (Default)**:
    - Spring matches a bean of the same type and injects it.
    - For example:
        `@Autowired private MyService myService;`
2. **By Name** (Using `@Qualifier`):
    - When multiple beans of the same type exist, Spring uses the bean name to resolve conflicts.
    - For example:
        `@Autowired @Qualifier("specificService") private MyService myService;`
3. **By Constructor**:
    - Dependencies are injected through the class constructor.
    - For example:
        `@Component public class MyController {     private final MyService myService;      @Autowired     public MyController(MyService myService) {         this.myService = myService;     } }`
4. **By Setter**:
    - Dependencies are injected via a setter method.
    - For example:
        `@Component public class MyController {     private MyService myService;      @Autowired     public void setMyService(MyService myService) {         this.myService = myService;     } }`
5. **Field Injection** (Directly into fields):
    - Dependencies are injected directly into fields using `@Autowired`.
    - For example:
        `@Component public class MyController {     @Autowired     private MyService myService; }`
---
### **Spring Autowiring Annotations**

1. **`@Autowired` (Core Annotation):**
    - Marks a dependency to be autowired by Spring.
    - Can be applied to fields, constructors, or setter methods.
2. **`@Qualifier` (Disambiguation):**
    - Used with `@Autowired` when there are multiple beans of the same type.
    - Example:
        `@Service("emailService") public class EmailService { }  @Service("smsService") public class SmsService { }  @Autowired @Qualifier("smsService") private NotificationService notificationService;`
3. **`@Primary` (Default Bean Selection):**
    - Marks a bean as the default choice when multiple candidates exist.
    - Example:
        `@Service @Primary public class EmailService { }`
4. **`@Resource` (JSR-250):**
    - Injects dependencies by name.
    - Example:
        `@Resource(name = "myBean") private MyService myService;`
---

