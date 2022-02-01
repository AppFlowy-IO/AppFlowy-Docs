# 📚 Technical Glossary

This glossary is where you will find definitions to the technical terms that are used in AppFlowy's code and technical documentation.

If you are looking for the terms used in the application, or in the user documentation you find them in the user [Glossary](broken-reference).

## A



| [Aggregate (DDD)](https://martinfowler.com/bliki/DDD\_Aggregate.html) | Note : Aggregate is a specific DDD term, and should not be confused with the aggregate design pattern. A DDD aggregate is a cluster of domain objects that can be treated as a single unit. Entities and Value objects can be grouped into aggregates. Aggregates can simplify the model by accessing the entire aggregate. For instance, Table has lots of rows. Each row using the table\_id to reference to the table. TableAggregate includes two entities: Table and the Row. |
| --------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

## B

|   |   |
| - | - |
|   |   |
|   |   |

## C

| cloned repo (git) | This is the clone that you create on your local machine.              |
| ----------------- | --------------------------------------------------------------------- |
| local repo (git)  | The repository that is on your machine. A synonum of **cloned repo.** |
|                   |                                                                       |

## D

| **doc** | @@@ [Nathan Foo](https://app.gitbook.com/u/HstpM3YrioTmnraZh6WT3tPRAN63 "mention") |
| ------- | ---------------------------------------------------------------------------------- |
| DDD     | Domain Driven Design                                                               |
|         |                                                                                    |

## E

| Entity (DDD) | Entities are plain objects that carry an identity which allows us to reference them. e.g. user, order, book, etc. You use entities to express your business model and encapsulate them into Factory that provides a simple API to create Entities. |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|              |                                                                                                                                                                                                                                                    |
|              |                                                                                                                                                                                                                                                    |

## F

| forked repo, fork (git) | An instance of a repository in your GitHub account that was created by using the forking mechanism. |
| ----------------------- | --------------------------------------------------------------------------------------------------- |
|                         |                                                                                                     |
|                         |                                                                                                     |

## G

|   |   |
| - | - |
|   |   |
|   |   |

## H

|   |   |
| - | - |
|   |   |
|   |   |

## I

|   |   |
| - | - |
|   |   |
|   |   |

## J

|   |   |
| - | - |
|   |   |
|   |   |

## K

|   |   |
| - | - |
|   |   |
|   |   |

## L

|   |   |
| - | - |
|   |   |
|   |   |

## M

|   |   |
| - | - |
|   |   |
|   |   |

## N

|   |   |
| - | - |
|   |   |
|   |   |

## O

| **origin (git)** | This is name of the git repository instance which is in your GitHub account. A repository in your account may have been created by you, or you may have forked it. |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|                  |                                                                                                                                                                    |
|                  |                                                                                                                                                                    |

## P

|   |   |
| - | - |
|   |   |
|   |   |

## Q

|   |   |
| - | - |
|   |   |
|   |   |

## R

| repo (git)       | A synonym for repository.                                                                                                                                                                                                                                                                                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Repository (DDD) | <p>Repositories offer an interface to retrieve and persist aggregates and entities. They hide the database or network details from the domain.<br><br>Repository interfaces are declared in the Domain Layer, but the repositories themselves are implemented in the Infrastructure Layer. You can replace the interface implementation without impacting the domain layer.</p> |
|                  |                                                                                                                                                                                                                                                                                                                                                                                 |
|                  |                                                                                                                                                                                                                                                                                                                                                                                 |

## S

| Service (DDD) | When a significant process of transformation in the domain is not a natural responsibility of an Entity or Value object, add an operation to the model as standalone interface declared as a Service. For instance: The Value object EmailAddress uses the function validateEmailAddress to verify if the email address is valid or not. Services exist in the Application, Domain and Infrastructure layers.  |
| ------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|               |                                                                                                                                                                                                                                                                                                                                                                                                                |
|               |                                                                                                                                                                                                                                                                                                                                                                                                                |

## T

|   |   |
| - | - |
|   |   |
|   |   |

## U

| **upstream** | This is the name of the original project's repository which is located in their GitHub account. |
| ------------ | ----------------------------------------------------------------------------------------------- |
|              |                                                                                                 |
|              |                                                                                                 |

## V

| Value Object | Value Object can't be referenced. They can be only included into entities and serve as attributes. Value objects should be simple and treated as immutable. e.g. email, phone number, name, etc. |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|              |                                                                                                                                                                                                  |
|              |                                                                                                                                                                                                  |

## W

|   |   |
| - | - |
|   |   |
|   |   |

## X

|   |   |
| - | - |
|   |   |
|   |   |

## Y

|   |   |
| - | - |
|   |   |
|   |   |

## Z

|   |   |
| - | - |
|   |   |
|   |   |

