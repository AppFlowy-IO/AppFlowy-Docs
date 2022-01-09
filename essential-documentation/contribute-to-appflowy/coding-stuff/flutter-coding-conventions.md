---
description: >-
  [Ed.] I have placed some @@@ in the text where I need Nathan's input. You can
  easily search for "@@@" to find them.
---

# Flutter Coding Conventions

### _Naming conventions_ <a href="#7a56" id="7a56"></a>

* _Classes, enums, typedefs, and extensions name should be in `UpperCamelCase.`_

```
class HomeLayout

enum IntegrationEnv {
  dev,
  pro,
}

typedef NaviAction = void Function();
```

* _Libraries, packages, directories, and source files name should be in `snake_case(lowercase_with_underscores).`_

```
library firebase_dynamic_links;
import ‘socket/socket_manager.dart’;
```

* _Variables, constants, parameters, and named parameters should be in `lowerCamelCase.`_

```
var item;

const testValue = 14.28;

final urlScheme = RegExp(‘^([a-z]+):’);

void sum(int testValue) {…}
```

### _Strings_ <a href="#2233" id="2233"></a>

* _PREFER using interpolation to compose strings and values._\
  _Generally, we are used to using long chains of `+` to build a string out of literals and other values. That does work in Dart, but it’s almost always cleaner and shorter to use interpolation:_

```
// Do

'Hello, $name! You are ${year - birth} years old.';
```

* _AVOID using curly braces in interpolation when not needed._\
  _If you’re interpolating a simple identifier not immediately followed by more alphanumeric text, the `{}` should be omitted._

```
// Don't

'Hello, ' + name + '! You are ' + (year - birth).toString() + ' years old.';
```

### _Variables_ <a href="#5dc0" id="5dc0"></a>

_@@@ We have to choose one of these two ideologies. Me, personally, I'm a type who writes the types. It makes the code easier to understand. I know that the newer mentality is to not have them because the compiler can figure it out. But where I disagree is that just because the compiler can figure it out, I don't see why we should make the next programmer have to figure it out. We'll do whatever you want :)_

#### _Specify types for class members_ <a href="#5dc0" id="5dc0"></a>

_Always specify the type of a member when it’s value type is known. Avoid using `var` when possible._

```
int item = 10;
final User user = User();
String name = ‘pooja’;
const int timeOut = 20;
```

### __ <a href="#2e62" id="2e62"></a>

```
d sum(int testValue) { // …}
```

### _Variables_ <a href="#2233" id="2233"></a>

DO follow a consistent rule for var and final on local variables. Most local variables shouldn’t have type annotations and should be declared using just var or final. There are two rules in wide use for when to use one or the other:

Use final for local variables that are not reassigned and var for those that are.

Use var for all local variables, even ones that aren’t reassigned. Never use final for locals. (Using final for fields and top-level variables is still encouraged, of course.)

Either rule is acceptable, but pick one and apply it consistently throughout your code. That way when a reader sees var, they know whether it means that the variable is assigned later in the function.

### _DON’T use `new`_ <a href="#2e62" id="2e62"></a>

> _Dart 2 makes the `new` keyword optional. Even in Dart 1, its meaning was never clear because factory constructors mean a `new` invocation may still not actually return a new object._
>
> _The language still permits `new` in order to make migration less painful, but consider it deprecated and remove it from your code._

```
//Do
Widget build(BuildContext context) {
  return Row(
    children: [
      RaisedButton(
        child: Text('Increment'),
      ),
      Text('Click!'),
    ],
  );
}

//Don't
Widget build(BuildContext context) {
  return new Row(
    children: [
      new RaisedButton(
        child: new Text('Increment'),
      ),
      new Text('Click!'),
    ],
  );
 }
```

### _Use `if` condition instead of conditional expression_ <a href="#905a" id="905a"></a>

_Many times we need to render a widget based on some condition in Row and Column. If **conditional expression** return null in any case then we should use the if condition only._

```
//Don't
Widget getText(BuildContext context) {
  return Row(
    children: [
      Text("Hello"),
      Platform.isAndroid ? Text("Android") : null,
    ]
  );
}


//Do
Widget getText(BuildContext context) {
  return Row(
    children:
      [
        Text("Hello"),
        if (Platform.isAndroid) Text("Android")
      ]
  );
}
```

### _Use Cascade Notation_ <a href="#405d" id="405d"></a>

__[_Cascade notation_](https://flutterbyexample.com/lesson/cascade-notation) _allows you to perform a sequence of operations on the same object. It saves your number of steps and needs for a temporary variable._

```
Demo d1 = new Demo();
Demo d2 = new Demo();

// Don't - Without Cascade Notation
d1.setA(20);
d1.setB(30);
d1.showVal();


// Do - With Cascade Notation
d2..setA(10)
  ..setB(15)
  ..showVal();
```

### _Use expression function bodies_ <a href="#2998" id="2998"></a>

_For functions that contain just one expression, you can use an expression function. The `=>` (arrow) notation is used for expression functions._

```
num get x => center.x;

set x(num value) => center = Point(value, center.y);
```

### _**Avoid large widget trees**_

_Split your code into smaller widgets instead. Dividing your code into small reusable widgets not only promotes its reusability but also its readability._

_In the example below, `EventItem` is a separate widget that will load individual events. `EventItem` is usually stored in a separate file._

```
itemBuilder: (ctx, i) => ChangeNotifierProvider.value(
  value: events[i],
  child: EventItem(),
 ),
```

### _**Utilities**_

_Place reusable functions in a class, so it's easy to access them. Also, For Dialog components, if you are using a package to wrap their logic with your own custom widget, so it would be easy to change the package if necessary later._

### _Const Widgets_ <a href="#44fa" id="44fa"></a>

_Whenever you have widgets that don’t change when the state changes, you should declare them as constants. This will prevent them from being rebuilt, hence improving performance._

_This is similar to caching widgets that won’t get rebuilt. Some of the widgets that can be declared as `const` include `Text`, `Padding`, and `Icons`, to mention a few. If the widgets contain dynamic information, they shouldn’t be declared as constants._

![Usage of const](https://miro.medium.com/max/553/1\*IdXs5sjANVB\_1g41D9vUug.png)

### _Remove Unused Resources_ <a href="#e66f" id="e66f"></a>

_Especially when you are ready to push your changes, you’ll need to remove resources that aren't used in the application. These could be image assets, for example. Removing unused resources and compressing images will help us reduce the size of the application._

### _Use Trailing Commas_ <a href="#8e4e" id="8e4e"></a>

_Since your widget tree can grow quickly, you need a way to format your code in a way that makes it easy to read. Adding trailing commas and using your IDE’s formatting shortcuts leads to more readablility._

![Usage of traiing commas](https://miro.medium.com/max/600/1\*vyVnQzEfD325-t-EPoll9g.png)

### _Render Grids and Lists Lazily_ <a href="#24b0" id="24b0"></a>

_Use the lazy methods, with callbacks, when building large grids or lists. That way only the visible portion of the screen is built at startup time._\
_Some ways to lazy load data_\
_- FutureBuilder_\
_- lazy\_load\_scrollview package_

### _**Flutter Analyze**_

_It’s important to check the code with the analyzer. Run `flutter analyze` in your terminal to check your code. This tool is a wrapper around the_ [_dartanalyzer_](https://www.dartlang.org/tools/analyzer) _tool. It performs static analysis of your code._

```
flutter analyze
```

_Note that the Continious Integration tasks will run flutter ananlyze on your PRs and will refuse tasks with warnings or errors._

### _Flutter Pub Version Checker (Android Studio Plugin)_ <a href="#d6ed" id="d6ed"></a>

_@@@ Is there a VS Code version o this? More importantly, what's our procedure? Do only you upgrage the versions?_

_Plugin for checking the latest Pub packages versions. It will automatically run inspection in your pubspec.yaml file to check all dependencies and compare versions with the latest versions from the Pub package repository. The highlighted ones need an update._

![pubspec.yaml](https://miro.medium.com/max/449/1\*qo0FSOOqHH-Zva8D-UAYvw.png)

### _Maintain hard-coded values, strings, colors in a separate file_ <a href="#bb17" id="bb17"></a>

_Create a separate dart file to store strings, colors, constants. so it’s easy to access them._

![colors.dart](https://miro.medium.com/max/624/1\*1K-AKulR7k8bQzyoWQOguA.png)

### _Custom Error Screen: handle “RED SCREEN OF DEATH”_ <a href="#8dad" id="8dad"></a>

_Use ErrorWidget that renders an exception’s message. This widget is used when a build method fails, to help determine where the problem lies. Exceptions are also logged to the console, which you can read using `flutter logs`. The console will also include additional information such as the stack trace for the exception._&#x20;

> _**It is possible to override this widget**. Refer to this_ [_article_](https://medium.com/nonstopio/flutter-kill-the-red-screen-of-death-f5e0601d1cdc) _for more information._

```
import 'package:flutter/material.dart';
void main() {
  ErrorWidget.builder = (FlutterErrorDetails details) {
    bool inDebug = false;
    assert(() { inDebug = true; return true; }());
    // In debug mode, use the normal error widget which shows
    // the error message:
    if (inDebug)
      return ErrorWidget(details.exception);
    // In release builds, show a yellow-on-blue message instead:
    return Container(
      alignment: Alignment.center,
      child: Text(
        'Error!',
        style: TextStyle(color: Colors.yellow),
        textDirection: TextDirection.ltr,
      ),
    );
  };
  // Here we would normally runApp() the root widget, but to demonstrate
  // the error handling we artificially fail:
  return runApp(Builder(
    builder: (BuildContext context) {
      throw 'oh no, an error';
    },
  ));
}
```
