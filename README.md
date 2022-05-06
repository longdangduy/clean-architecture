# clean-architecture
## 1. What is The Clean Architecture?
The Clean Architecture is the software architecture idea proposed by Robert C. Martin (Uncle Bob). This architecture divides the software into layers. 
And these layers are built base on **The Dependency Rule**.

This rule says that:
<code>Source code dependencies must point only inward, toward higher-livel policies.</code>

That means nothing in an inner circle can know anything at all about something in an outer circle. 
In particular, the name of something declared in an outer circle must not be mentioned by the code in the an inner circle. 
That includes, functions, classes. variables, or any other named software entity.
And one more thing, all dependencies should be interface.

The below diagram is an attempt at integrating all these architectures into a single actionable idea.
![The Clean Architecture](https://user-images.githubusercontent.com/36881424/166196851-1985b9f4-0bd6-40d9-bfc1-e844455379ed.png)

### Entities
Entities encapsulate *Enterprise-wide* **Critial Business Rules**. An entity can be an object with methods, or it can be a set of data structures and functions. 
It doesn’t matter so long as the entities could be used by many different applications in the enterprise.


### Use Cases
The software in this layer contains *Application-specific* business rules. It encapsulates and implements all of the use cases of the system. 
These use cases orchestrate the flow of data to and from the entities, and direct those entities to use their enterprise wide business rules to achieve the goals of the use case.


### Interface Adapters
The software in this layer is a set of adapters that convert data from the format most convenient for the use cases and entities, to the format most convenient for some external agency such as the Database or the Web. 

It is this layer, for example, that will wholly contain the MVC architecture of a GUI. The Presenters, Views, and Controllers all belong in here. 
The models are likely just data structures that are passed from the controllers to the use cases, and then back from the use cases to the presenters and views.


### Frameworks and Drivers
The outermost layer is generally composed of frameworks and tools such as the Database, the Web Framework, etc. 
Generally you don’t write much code in this layer other than glue code that communicates to the next circle inwards.


## 2. Characteristics of Clean Architecture
This architecture produces software that have follow characteristics:
- Independent of Frameworks: the architecture does not depend on the existence of some library of feature laden software. This allows you to use such frameworks as tools, rather than having to cram your system into their limited constraints.

- Independent of UI: the UI can change easily, without changing the rest of the system. A Web UI could be replaced with a console UI, for example, without changing the business rules.

- Independent of Database: you can swap out Oracle or SQL Server, for Mongo, BigTable, CouchDB, or something else. Your business rules are not bound to the database.

- Independent of any external agency: in fact your business rules simply don’t know anything at all about the outside world.

- Testable: the business rules can be tested without the UI, Database, Web Server, or any other external element.


## 3. How to implement



## 4. Pros and Cons 



## 5. Compare with N-Tier Architecture



## 6. Applicability



**References:**
https://www.amazon.com/Clean-Architecture-Craftsmans-Software-Structure/dp/0134494164
