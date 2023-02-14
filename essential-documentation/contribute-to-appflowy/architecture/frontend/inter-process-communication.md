# Inter-Process Communication

AppFlowy uses a particular style of Inter-Process Communication called [Asynchronous Message Passing](https://en.wikipedia.org/wiki/Message\_passing#Asynchronous\_message\_passing), where processes exchange requests and responses are serialized using the **Protobuf** representation.

Message passing is a safer technique than shared memory or direct function access because the recipient is free to reject or discard requests as it sees fit. For example, if the Flowy Core determines a request is invalid, it simply discards the requests and never executes the corresponding function. This article is going to explain how the event process works.

## Events

AppFlowy's backend defines all the events and generates the event's [foreign function interface](https://en.wikipedia.org/wiki/Foreign\_function\_interface). Currently, AppFlowy supports **Dart** and **TS** event call.

Events are emitted in the frontend and are processed in the backend. Each event has its own handler in the backend. Each event can carry a payload that is serialized using protobuf. This payload will be deserialized in the backend using the corresponding protobuf struct.

Please check out [this](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/architecture/backend/event) if you want to know the details of the events.

![file : inter\_process\_communication.plantuml](../../../../.gitbook/assets/inter\_process\_commuciate-Events.svg)

For example, using `UserEventSignIn` to trigger event with passed-in parameter in the backend.

```typescript
async function sendSignInEvent() {
    let make_payload = () =>
        SignInPayloadPB.fromObject({
            email: nanoid(4) + "@gmail.com",
            password: "A!@123abc",
            name: "abc",
        });
    await UserEventSignIn(make_payload());
}
```

## Notifications

Notifications one-way messages that are best suited to communicate lifecycle events and state changes. Notifications are triggered in the backend and received in the frontend. Each notification can carry payload that is serialized using protobuf. This payload will be deserialized in the frontend using the corresponding protobuf struct.

![file : inter\_process\_communication.plantuml](../../../../.gitbook/assets/inter\_process\_commuciate-Notifications.svg)

For example, using `UserNotificationListener` to receive notifications when new user signs in.

```typescript
 let listener = await new UserNotificationListener({
    onUserSignIn: (userProfile) => {
        console.log(userProfile);
    }, 
    onProfileUpdate(userProfile) {
        console.log(userProfile);
        // stop listening the changes
        // listener.stop();
    }}
);

listener.start();
```
