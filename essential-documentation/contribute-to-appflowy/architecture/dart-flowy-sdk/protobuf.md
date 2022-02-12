
# Flowy Protobuf

## Exchange Data
The article introduces how AppFlowy uses protobuf buffer. AppFlowy front-end written in Flutter and the back-end written in Rust,
they exchange data through the FFI. Look at the picture shown below,
![file : event_map.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/feat/pb/uml/output/FlowySDK-FFI.svg)
1. Front-end's repository triggers the event with the Protobuf.
2. Front-end's FFI serializes the protobuf to bytes and sends the event and bytes to the back-end side.
3. Back-end's FFI deserializes the bytes to the protobuf and passes the event and protobuf to Dispatcher.
4. Dispatcher sends the protobuf to the module that can handle the event. 


## Generate Process
![file : event_map.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/feat/pb/uml/output/FlowySDK-Protobuf_Code_Generation.svg)


