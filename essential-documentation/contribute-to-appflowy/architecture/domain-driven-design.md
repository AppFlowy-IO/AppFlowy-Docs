# Domain Driven Design

For many architects, the process of data modeling is driven by intuition. However, there are well-formulated methodologies for approaching it more formally. We chose [Domain-Driven Design](https://en.wikipedia.org/wiki/Domain-driven\_design) for AppFlowy's architecture.

## :boom: Layered architecture

The most common architecture pattern is the layered architecture pattern, known as the n-tier architecture pattern, where we partition the software into `layers` to reduce the complexity. Each layer of the layered architecture pattern has a specific role and responsibility.`DDD` consists of four layers.

![file : ddd\_layered\_achitecture.wsd](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/DDDLayeredArchitecture.svg)

### **Presentation Layer**:

* Responsible for presenting information to the user and interpreting user commands.
* Consists of Widgets and also the state of the Widgets.

### **Application Layer**:

* Defines the jobs the software is supposed to do. (Shouldn't find any UI code or network code)
* Coordinates the application activity and delegates work to the next layer down.
* It doesn't contain any complex business logic but the basic validation of user input before passing it to the other layers.

### **Domain Layer**:

* Responsible for representing concepts of the business.
* Manages the business state or delegates to the infrastructure layer.
* Self contained and it doesn't depend on any other layers. The Domain layer should be well isolated from the other layers.

### **Infrastructure Layer**:

* Persists application data by implementing the repository interfaces provided by the Domain layer.
* Provides generic technical capabilities that support the higher layers. It deals with APIs, persistence and network, etc.
* Hides the complexity of the Domain layer.

AppFlowy is composed in layers, where higher layers use the facilities provided by lower layers. Each layer provides a different abstraction from the layer above and below it. As you can see, the `Complexity` and `Abstraction` of these layers are depicted in the following diagram. As developers, we should pull the complexity downwards. Simple interfaces and powerful implementations (Think about the [open](https://man7.org/linux/man-pages/man2/open.2.html) function). Another way of expressing this idea is that it is more important for a module to have a simple interface than a simple implementation.

```
                 ▲
                 │
    Level of     ├───────────────────┐
    Abstraction  │ Presentation      │
                 ├───────────────────┴───────┐
                 │ Application               │
                 ├───────────────────────────┴─────────┐
                 │ Domain                              │
                 ├─────────────────────────────────────┴────────┐
                 │ Infrastructure                               │
                 └──────────────────────────────────────────────┴─────▶
                                                           Complexity
```

### Data Model

DDD classifies data as referenceable objects, or entities, and non-referenceable objects, or value objects. Let's introduce some DDD terminology.

**Entity**

`Entities` are plain objects that carry an identity which allows us to reference them. e.g. user, order, book, etc. You use `entities` to express your business model and encapsulate them into Factory that provides a simple API to create Entities.

**Value Object**

`Value Object` can't be referenced. They can be only included into entities and serve as attributes. Value objects should be simple and treated as immutable. e.g. email, phone number, name, etc.

**Aggregate**

`Entities` and `Value objects` can be grouped into aggregates. Aggregates can simplify the model by accessing the entire aggregate. For instance, Table has lots of rows. Each row using the table\_id to reference to the table. TableAggregate includes two entities: Table and the Row.

```
     TableAggregate
    ┌────────────────────────────────────────────────────────────────┐
    │                                                                │
    │  ┌────────────────────┐         ┌─────────────────────────┐    │
    │  │struct Table {      │         │struct Row {             │    │
    │  │    id: String,     │         │    table_id: String,    │    │
    │  │    desc: String,   │◀▶───────│}                        │    │
    │  │}                   │         │                         │    │
    │  └────────────────────┘         └─────────────────────────┘    │
    │                                                                │
    └────────────────────────────────────────────────────────────────┘
```

**Service**

When a significant process of transformation in the domain is not a natural responsibility of an `Entity` or `Value object`, add an operation to the model as standalone interface declared as a Service. For instance: The `Value object` EmailAddress uses the function `validateEmailAddress` to verify if the email address is valid or not. `Services` exist in the Application, Domain and Infrastructure layers.

```
class EmailAddress  {
  final Either<Failure<String>, String> value;

  factory EmailAddress(String? input) {
    return EmailAddress._(
      validateEmailAddress(input),
    );
  }

  const EmailAddress._(this.value);
}


Either<Failure<String>, String> validateEmailAddress(String? input) {
  ...
}
```

**Repository**

Repositories offer an interface to retrieve and persist aggregates and entities. They hide the database or network details from the domain.

Repository interfaces are declared in the Domain Layer, but the repositories themselves are implemented in the Infrastructure Layer. You can replace the interface implementation without impacting the domain layer.

For instance:

```
// Interface:
abstract class AuthInterface {
    ...
}

// Implementation
class AuthRepository implements AuthInterface {
    ...
}
```

> More often than not, the repository interface can be divided into sub-repository in order to reduce the complexity.

### Relation

The diagram below is a navigational map. It shows the patterns that form the building blocks of Domain Driven Design and how they relate to each other.

## Operation Flow

```
       presentation       │          Application                      domain                        Infrastructure
                                                      │                                   │
                             7                                 Data Model
               ┌──────────────────────────────┐       │       ┌────────────────────────┐  │     ┌─────────────────────┐
               │          │                   │               │ ┌─────────────┐        │        │   Network Service   │
               ▼             Bloc             │       │       │ │  Aggregate  │        │  │     └─────────────────────┘
        ┌─────────────┐   │ ┌─────────────────┴─────┐         │ └─────────────┘        │                   ▲
────────▶   Widget    │     │ ┌────────┐ ┌────────┐ │    2    │ ┌────────┐             │  │                │ 6
        └─────────────┘   │ │ │ Event  │ │ State  │ │────┬───▶│ │ Entity │             │        ┌─────────────────────┐
User           │            │ └────────┘ └────────┘ │ │  │    │ └────────┘             │  │     │ Persistence Service │
interaction    │          │ └──────▲────────────────┘    │    │ ┌─────────────────┐    │        └─────────────────────┘
               │                   │                  │  │    │ │  Value Object   │    │  │                ▲
               └──────────┼────────┘                     │    │ └─────────────────┘    │                   │ 5
                     1                                │  │    └────────────◈───────────┘  │     ┌─────────────────────┐
                          │                              │                 │contain             │    Unit of Work     │
                                                      │  │      ┌────────────────────┐    │     └─────────────────────┘
                          │                              │      │      Service       │                     ▲
                                                      │  │      └────────────────────┘    │                │
                          │                              │                                                 │ 4
                                                      │  │     Repository                 │                │
                          │                              │   ┌─────────────────────────────────────────────┴───────────────┐
                                                      │  │   │ ┌ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┐  3  ┌ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┐ │
                          │                              └───┤         Interface        ────▶       Implementation         │
                                                      │      │ └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┘     └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┘ │
                          │                                  └─────────────────────────────────────────────────────────────┘
                                                      │
```

1. Widget accepts user interaction and translates the interactions into specific Events. The events will be sent to the Application layer, handled by the specific `bloc`. The `bloc` sends the states changed by the events back to the widget, and finally the `Widget` updates the UI according to the state. The pattern is depicted in this diagram. (More about the flutter [bloc](https://bloclibrary.dev/#/coreconcepts?id=bloc))

![file : DDDBlocCPattern.svg](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/DDDBLoCPattern.svg)

2\. The `bloc` processes the events using the services provided by the `Domain` layer.

1. Convert DTO (Data Transfer Object) to domain model and Domain Model to DTO.
2. Domain model is the place where all your business logic, business validation and business behaviors will be implemented. The Aggregate Roots, Entities and Value Objects will help to achieve the business logic.

3\. Calling repositories to perform additional operations. The repositories interfaces are declared in the `Domain` layer and are implemented in the `Infrastructure` layer. You can reimplement the repository interface with different languages, such as `Rust`, `C++` or `Dart`. etc.

![file : DDDRepositoryImplementsInterface.svg](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/DDDRepositoryImplementsInterface.svg)

4\. The responsibility of [Unit of Work](https://martinfowler.com/eaaCatalog/unitOfWork.html) is to maintain a list of objects affected by a business transaction and coordinates the writing out of changes and the resolution of concurrency problems((No intermediate state)). If any one persistence service fails, the whole transaction will be failed so, roll back operation will be called to put the object back in initial state.

1. Handling operations (INSERT, UPDATE and DELETE) with SQLite to persis the data.
2. Saving or querying the data in the cloud to finish the operation.
