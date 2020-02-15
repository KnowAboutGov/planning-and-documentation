# Notes about the Spring Boot Java Framework
## Prerequisite Concepts
### Dependency Injection (DI)
* Decouples classes with its dependencies
    * __Dependency:__ If class A uses some methods of class B (after creating an instance of new B), then B is a dependency of class A
* The dependency is created __outside__ of the dependent class
* The dependent class only __uses__ the injected dependency, it does create or instantiate it
* Dependencies with DI get injected at runtime not at complie time
[Tutorial with DI](https://www.journaldev.com/2394/java-dependency-injection-design-pattern-example-tutorial)

## Project Structure
Taken from spring docs
```
com
  +- tyler
      +- myapp
          +- Application.Java (Entry Point)
          |
          +- Customer (Package)
          |   +- Customer.java (Data Model)
          |   +- CustomerController.Java (MVC Controller)
          |   +- CustomerService.Java (__Not sure__)
          |   +- CustomerRepository.Java (__Learn More__ links data model with db)
          +- Order (Package)
              +- Order.Java (Data Model)
              +- OrderController.Java (MVC Controller)
              +- OrderService.Java (__Not sure__)
              +- CustomerRepository.Java (__Learn More__ links data model with db)
    
```
