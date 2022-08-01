# Delta

The crate `lib-ot` located in the `shared-lib/lib-ot`. It has a `Delta` struct that can be used to describe contents
and changes. The format of `Delta` is JSON based, and is human readable, it can describe any rich text document,
includes all text and formatting information.


![file : delta.plantuml](../../../../uml/output/Delta.svg)


A Delta contains a list of operations, which describe the changes to a document. There are three kinds of operations,
insert, delete, and retain.

## Operation
Operation contains three types, **Insert**, **Delete**, and **Retain**. 

### Insert
Insert operations have an insert key defined. A String value represents inserting text. an optional attributes key can 
be defined with an Object to describe additional formatting information. Formats can be changed by the retain operation.

### Delete
Delete operations have a Number delete key defined representing the number of characters to delete.


### Retain
Retain operations have a Number retain key defined representing the number of characters to keep An optional attributes
key can be defined with an Object to describe formatting changes to the character range. A value of null in the
attributes Object represents removal of that key.



## DeltaIterator


## OTString

## Attributes

### RichTextAttributes

### PhantomAttributes

## OperationTransform
https://en.wikipedia.org/wiki/Operational_transformation
