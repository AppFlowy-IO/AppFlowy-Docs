# 🥳 Event Driven System

## :dart: Goals of the System

The AppFlowy project is an attempt to build a high performance application. Here are the top-level requirements for our system.

1. **High Performance.**
2. **Cross-platform.**
3. **Reliability.**
4. **Safety.**

## :thinking: Some Design Considerations

## :scroll: High Level Design

## 📚 Component Design

### 📙 Event Dispatch

![file : event\_dispatch.wsd](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/EventDispatch.svg)

Here is the event flow:

1. User clicks on a `Widget`(The user interface) that invokes the `Bloc` actions.
2. `Bloc` calls the repositories to perform additional operations to handle the actions.
3. `Repository` offers the functionalities by combining the event, defined in the `FlowySDK`.
4. `Events` are be passed in the `FlowySDK` through the [FFI](https://en.wikipedia.org/wiki/Foreign\_function\_interface) interface.
5. `Dispatcher` parses the event and generates the specific action scheduled in the `FlowySDK` runtime.
6. `Dispatcher` finds the event `Handler` declared by the `Modules`.
7. `Handler` consumes the event and generates the response. The response will be returned to the widget through the `FFI`.

The event flow will be discussed in two parts: the frontend implemented in flutter and the FlowySDK implemented in Rust.

### :technologist: FlowySDK

#### Frontend

The Frontend follows the DDD design pattern, you can recap from [domain-driven-design.md](domain-driven-design.md "mention")

![file : eventdispatchfrontend.wsd](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/EventDispatchFrontend.svg)
