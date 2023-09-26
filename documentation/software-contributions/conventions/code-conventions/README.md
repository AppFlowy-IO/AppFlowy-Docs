# ⌨ Code Conventions

## Variables

In the AppFlowy codebase, we prioritise variable immutability and consistency. This approach is integral to our code conventions, enhancing code quality and maintainability.

As much as you can, prefer declaring variables as immutable. This is done in Flutter by the use of the \`final\` keyword, and in Rust by omitting the \`mut\` keyword.

In the case you prefer specifying the type of immutable variables, please do this consistently throughout your code. For immutable variables, **always** specify the type.

By adhering to these principles, we create a codebase that is not only functional but also comprehensible and maintainable for all team members.

## Use Cascade Notation  <a href="#405d" id="405d"></a>

[Cascade notation](https://flutterbyexample.com/lesson/cascade-notation) allows you to perform a sequence of operations on the same object. It saves your number of steps and needs for a temporary variable.

### Flutter

```
Demo d1 = new Demo();
Demo d2 = new Demo();

// Bad - Without Cascade Notation
d1.setA(20);
d1.setB(30);
d1.showVal();


// Good - With Cascade Notation
d2..setA(10)
  ..setB(15)
  ..showVal();
```

### Rust <a href="#2998" id="2998"></a>

```
let mut person = Person::new();
let mut numbers = Vec::new();

// Bad - Without Cascade Notation
person.set_name("Alice");
person.set_age(30);
person.print_info();

numbers.push(1);
numbers.push(2);
numbers.push(3);

// Good - With Cascade Notation
person
    .set_name("Alice")
    .set_age(30)
    .print_info(); 

numbers
    .push(1)
    .push(2)
    .push(3);
```

## Use expression bodies  <a href="#2998" id="2998"></a>

For functions that contain just one expression, you can use an expression function. The `=>` (arrow) notation is used for expression functions.

### Flutter

```
// Good
setState(() => performAction(someValue));

// Bad:
setState(() {
  performAction(someValue);
});
```

### Rust

```
// Good
some_function(|| perform_action(some_value));

// Bad
some_function(|| {
    perform_action(some_value);
});
```

## Inline TODOs

We prefer _**not**_ including inline todos in the codebase, however, whilst you're developing feel free to add TODOs.

When opening a PR, please try to resolve the TODOs you created, if they need more attention or are more complex, then you can remove the TODO in favor of opening an issue on Github.

## Dependencies and Crates
