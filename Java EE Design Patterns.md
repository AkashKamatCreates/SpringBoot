- GOF: gang of four design pattern are divided into 3: creation, structural and behavioural patterns. 
- design patterns are important tool in a programmers toolbox.
- design patterns helps us solve recurring common known problems with a software. however, not every app should apply every design pattern since it tends to overcomplicate things. 
- gang of four:
	- creational patterns
		- creation
		- initialization
		- class selection
	- behavioural:
		- interactions between objects
	- structural
		- relationaships and ocmbining
-  ![[Pasted image 20241222104400.png]]
- another type of design pattern is enterprise pattern: these are patterns specifically made to solve enterprise software problems.
	- They follow flow of message throughout the program. mvc pattern, classified by application lyer. 
- enterprise patterns solve the problems which will definitely come to an enterprise project while developing. thus using the enterprise patterns will save the org a lot of time in avoiding / solving common recurring problems that are bound to come with nature of enterprise applications. 

# Singleton pattern
- single object in the jvm
- global point of access
- construct heavy weight objects. 
- create once, always available
- in java SE, its implementation is not easy. its made easy in EE with a single annotation @singleton
- ![[Pasted image 20241222111531.png]]
- **Use of singleton beans**:  
	- **Efficiency**: For expensive-to-create objects (like database connections), having a pool means you don't have to create a new object each time one is needed. This reduces the time and resources spent on object creation.
	- **Resource Management**: An object pool ensures that a fixed number of objects are available, preventing the application from running out of resources or creating too many objects, which could lead to memory issues.

# Facade design pattern:
- **Unified Interface**: The facade pattern provides a simple and unified interface to a set of interfaces in a subsystem, hiding the complexity of the subsystem.
	- **Simplified Access**: It is commonly used to provide easy access to a legacy back-end system by combining multiple services into a higher-level service, reducing the number of remote network calls.
	- **Banking Example**: The video uses a banking scenario where a facade simplifies the process of approving a loan by making multiple subsystem calls behind the scenes, demonstrating how the facade pattern can streamline complex processes.
# observer design pattern:
- The **Observer Design Pattern** is like a **"subscribe and notify" system**. It helps one part of your program (called the **Subject**) to automatically notify other parts (called **Observers**) when something changes. 
# decorator design pattern:
- The **Decorator Design Pattern** is used to add new functionality to an object **dynamically** at runtime, without changing its structure. This is done by "wrapping" the object with other objects (decorators) that enhance or modify its behavior.

# Enterprise design patterns
- mvc
- integration, architectural patterns
# Dependency injection pattern
- based on inversion of control
- implementation independent
- unit testing easier
- loosely coupled
- change where objects are created
- eases plumbing and wiring of the project. 
- managed bean specification 
- it has its own features and limitations. 
- springboot heavily uses them. 
# filter design pattern
The **Filter Design Pattern** is a behavioral pattern used to filter a stream of data based on a set of criteria. It is commonly used when you need to apply multiple filters in a chain, and each filter can be independent of others.

In Java EE, the **Filter Design Pattern** is often used in **servlets** to process requests and responses. The filter is a component that intercepts HTTP requests and/or responses, providing the ability to modify or log them, apply security checks, and other functionalities.

In Java EE, **Servlet Filters** are used to implement this pattern. A filter allows developers to **intercept and modify HTTP requests and responses** before they reach the servlet or after the servlet processes them.
- **Purpose**: The filter design pattern is used for pre-processing and post-processing of requests and responses in Java EE applications, often for tasks like authentication, logging, compression, and encryption.
- **Implementation**: Filters are implemented by creating a class that implements the `javax.servlet.Filter` interface and its methods (`init`, `doFilter`, and `destroy`).
- **Usage**: Filters can be chained together and configured using the `@WebFilter` annotation or in the `web.xml` deployment descriptor to specify the order of execution and the URL patterns they apply to.
# AOP aspect oriented programming interceptor pattern
The **AOP (Aspect-Oriented Programming) Interceptor Pattern** is a design pattern used to **separate concerns** in software development. It allows you to define cross-cutting concerns (like logging, security, transaction management, etc.) in a way that doesn't require modifying the core business logic.

An **interceptor** is a type of **aspect** in AOP. It is a piece of code that intercepts method calls or events and can perform actions before or after the method execution.

In **Java EE** (especially with **CDI**), interceptors are used to provide a mechanism to add additional behavior to beans at runtime. They can be used for tasks like logging, security, transaction management, etc., without modifying the underlying bean's code.

### Key Characteristics of Interceptors in AOP:

1. **Interception**: Interceptors can modify the execution of methods before and after the method call.
2. **Separation of Concerns**: They allow you to separate cross-cutting concerns from the business logic.
3. **Reusability**: Interceptors can be reused across different classes.
### **MVC (Model-View-Controller) Pattern** and **Front Controller Pattern**

The **MVC** (Model-View-Controller) pattern and the **Front Controller** pattern are both widely used in web application architectures. While they serve different purposes, they are often used together to create maintainable, scalable, and well-organized applications.

**1. MVC (Model-View-Controller) Pattern**

The **MVC pattern** is a way of separating the concerns of an application into three main components: **Model**, **View**, and **Controller**. This separation helps manage complexity by organizing code around the different responsibilities of the application.

- **Model**: Represents the application's data and business logic. It is responsible for retrieving, updating, and storing data, often interacting with the database. It is **independent of the UI** and does not know about the view or controller.
    
- **View**: Represents the user interface (UI). It displays data from the model and provides an interface for the user to interact with. The view is updated when the model changes, typically using events or data binding.
    
- **Controller**: Acts as an intermediary between the Model and View. It handles user input, manipulates data from the model, and updates the view. It receives input from the view, processes it (usually by calling the model), and updates the view accordingly.
    

 **Flow in MVC**:

1. The **view** sends a request (usually user input) to the **controller**.
2. The **controller** processes the input, manipulates the **model**, and updates the **view**.
3. The **model** responds with data that the **controller** uses to update the **view**.

---

**2. Front Controller Pattern**

The **Front Controller** pattern is a design pattern that provides a centralized entry point for handling all requests in an application. In web applications, this typically refers to a single **controller** or **servlet** that handles all HTTP requests and delegates them to appropriate handlers or views.

- **Centralized Request Handling**: Instead of having multiple controllers for different views or functionalities, a single controller intercepts all incoming requests. This controller then decides how to route the request to the appropriate handler or service.
    
- **Routing Logic**: The front controller handles the routing of requests to specific views or business logic classes. This helps keep the application centralized and modular.
    

---

**How MVC and Front Controller Pattern Work Together**

The **Front Controller Pattern** is often used in conjunction with the **MVC pattern** to handle web requests in a centralized manner and forward them to the appropriate controller in the MVC architecture.

In such a setup, the **front controller** acts as the entry point for all requests. It takes the incoming requests, determines the appropriate **controller** to process the request, and delegates the processing to that controller. Once the controller processes the request, it updates the **model** and forwards the data to the **view** for rendering.

