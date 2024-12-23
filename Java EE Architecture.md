# Domain Architecture Notes

## Data-Centric Architecture
- Centers the architecture around the data layer.
- The application logic is designed to primarily manipulate and interact with the database.
- Suitable for CRUD-heavy applications.
- **Java EE Example**: Use of JPA or Hibernate for ORM.

## Classic Three-Tiered Architecture
- Divides the application into three main layers:
    1. **Presentation Layer**: Handles user interface (e.g., JSP, JSF).
    2. **Business Logic Layer**: Processes business rules (e.g., EJB).
    3. **Data Access Layer**: Manages database interactions (e.g., JPA).
- **Pros**:
    - Clear separation of concerns.
    - Scalable and maintainable.
- **Cons**:
    - Can introduce latency due to multiple layers.

## Domain-Centric Architecture
- Focuses on the domain model and encapsulates business logic within the domain layer.
- Often implemented with Domain-Driven Design (DDD).
- **Key Concepts**:
    - Aggregates, Entities, Value Objects.

## Modern Four-Layer Architecture
- Adds an additional layer to the classic architecture:
    1. **Presentation**: User-facing interfaces.
    2. **Application**: Coordinates requests and manages flows.
    3. **Domain**: Core business rules and logic.
    4. **Infrastructure**: External systems, database, etc.

## Types of Domain Architecture
### Screaming Architecture
- Emphasizes clarity of the domain in code structure.
- Focuses on business concerns rather than technical aspects.

### Functional vs. Categorical
- **Functional**: Organizes code by use-case or functionality.
- **Categorical**: Groups code by category (e.g., controllers, services, repositories).

## CQRS Architecture
- **Command Query Responsibility Segregation**:
    - Separates read and write operations into different models.
- **Variants**:
    1. Basic: Separate read/write models in the same system.
    2. Event Sourcing: Tracks state changes as events.
    3. Hybrid: Combines CQRS with traditional methods.
- **Pros**:
    - Improved performance.
    - Scalability.
- **Cons**:
    - Increased complexity.

## Monolith and Microservice Architecture
- **Monolith**:
    - Single deployable unit.
    - **Pros**: Simple to develop, deploy, and test.
    - **Cons**: Hard to scale and modify.
- **Microservices**:
    - Breaks application into small, independent services.
    - **Pros**: Scalability, flexibility.
    - **Cons**: Requires advanced deployment strategies and monitoring.
- **Java EE Example**:
    - Monolith: Traditional EJB application.
    - Microservices: Use of Spring Boot and Docker/Kubernetes.

