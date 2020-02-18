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
## FreeMarker Template Engine
* <# import "/spring.ftl" as spring /> to bring in the spring ftl macros
      * This brings in the spring macros to use with the template engine freemarker
* __Note:__ The default file extension that ViewResolver looks for .ftlh NOT .ftl files

Spring Macro | ftlh
--- | ---
message | <@spring.message code/>
messageText | <@spring.messageText />
url | <@spring.url relativeUrl />
formInput | <@spring.formInput path, attributes, fieldType/>
formHiddenInput | <@spring.formHiddenInput path, attributes />
formPasswordInput | <@spring.formPasswordInput path, attributes />
formTextArea | <@spring.formTextArea path, attributes />


## Using JDBC with Spring (For MySql on local device or across LAN)
In the application.properties file ({$CONTAINING_DIR}project/src/main/resources),
the following lines to be added (*This works for localhost*)
```
spring.jpa.hibernate.ddl-auto=update
spring.datasource.url=jdbc:mysql://${MYSQLHOST:${host}:3306/${database_name}
spring.datasource.username=${user}
spring.datasource.password=${password}
```
- [ ] Figure out how to omit passwords from version control
## Miscellaneous Notes
### Changing Dependencies in Maven
To add dependencies in Maven project using intellij IDEA...
1. Open pom.xml
2. alt+insert or right click -> generate
3. dependency
4. search for dependency
5. rebuild project
