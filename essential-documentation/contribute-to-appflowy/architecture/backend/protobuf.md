# Protobuf-FlowySDK

The article introduces how AppFlowy uses protobuf buffer to exchange the data between Dart and Rust. The pattern as
shown below:

![file : event_map.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/FlowySDK-FFI.svg)

Front-end written in Dart and Back-end written in Rust, they communicate with each other using the protocol buffer.
Let's dig into the details.

## Generate Process
Let's introduce the generating process that consists of three parts.

![file : event_map.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/FlowySDK-Protobuf_Code_Generation.svg)

### Part One
We define the `Event` and the `Protobuf data struct` in Rust, for example, the `TextBlockEvent` defined in event_map.rs and `ExportData` defined in entities.rs.

```rust
// event_map.rs
pub enum TextBlockEvent {
    #[event(input = "TextBlockIdPB", output = "TextBlockDeltaPB")]
    GetBlockData = 0,

    #[event(input = "TextBlockDeltaPB", output = "TextBlockDeltaPB")]
    ApplyDelta = 1,

    #[event(input = "ExportPayloadPB", output = "ExportDataPB")]
    ExportDocument = 2,
}

```
The annotation, `#[event(input = Input struct, output = Output struct)]` is used to generate the dart function.

* `Input struct` mean the function receive the input parameter's type.
* `Output struct` mean the function's return value's type

I think you noticed that there is a`PB` keyword appended to every struct. We use the `PB` keyword to identify
this struct is in protobuf format.

```rust
// entities.rs
#[derive(Default, ProtoBuf)]
pub struct ExportDataPB {
    #[pb(index = 1)]
    pub data: String,

    #[pb(index = 2)]
    pub export_type: ExportType,
}

```

The procedural macro, `ProtoBuf`, is used to mark this struct is going to generate the protobuf struct.


> We use the [syn](https://docs.rs/syn/latest/syn/) to collect the [AST](https://en.wikipedia.org/wiki/Abstract_syntax_tree) information that will be used to generate
the `proto file`. If you interest in how to collect the information in details, you should check out the [Procedural Macros](https://doc.rust-lang.org/reference/procedural-macros.html).

### Part Two
[Build Scripts](https://doc.rust-lang.org/cargo/reference/build-scripts.html) is the perfect way to do the code generation.
Let's check out some pseudocode.

```Rust
// build.rs

fn main() {
    code_gen::protobuf_file::gen(env!("CARGO_PKG_NAME"));
}


fn gen(crate_name: &str, proto_file_dir: &str) { 
    // 1. generate the proto files to proto_file_dir
    let _ = gen_protos(crate_name);

    // 2. generate the protobuf files(Dart)
    generate_dart_protobuf_files(crate_name, proto_file_dir, &paths, &file_names, &protoc_bin_path);
    
    // 3. generate the protobuf files(Rust)
    generate_rust_protobuf_files(&protoc_bin_path, &paths, proto_file_dir);
}
```



### Part Three
You may wonder how build.rs define which files should generate the proto files and the event code(on the Dart side).
Well, we use the config file to achieve this.


```toml
proto_input = ["src/event_map.rs", "src/entities.rs"]
event_files = ["src/event_map.rs"]
```

**proto_input** 

The proto_input receives path or file. The `code gen` process will parse the proto_input in order to generate the struct/enum.

**event_files**

The event_files receives file that define the event. The `code gen` process will parse the file in order to generate the
dart event class.

The event class name consists of the Enum name and the Enum value defined in event_map.rs. 

    For example: The ExportDocument event: 
    ```Dart
    class TextBlockEventExportDocument {
         ExportPayload request;
         TextBlockEventExportDocument(this.request);
    
        Future<Either<ExportData, FlowyError>> send() {
        final request = FFIRequest.create()
              ..event = TextBlockEvent.ExportDocument.toString()
              ..payload = requestToBytes(this.request);
    
        return Dispatch.asyncRequest(request)
            .then((bytesResult) => bytesResult.fold(
               (okBytes) => left(ExportData.fromBuffer(okBytes)),
               (errBytes) => right(FlowyError.fromBuffer(errBytes)),
            ));
        }
    }
    
    ```

### Part Four

The `code gen` process is embedded in the AppFlowy build process. But you can run the build process manually. 
Just go to the corresponding crate directory(For example, frontend/flowy-text-block), and run:

`cargo build --features=dart`

or if you want to check the verbose output.

`cargo build -vv --features=dart`

The build scripts will be run before the crate gets compiled. Thanks to the cargo toolchain, we use `cargo:rerun-if-changed=PATH`
to enable the build.rs will only run if the files were changed.

> [cargo:rerun-if-changed=PATH](https://doc.rust-lang.org/cargo/reference/build-scripts.html#rerun-if-changed)
>
> The rerun-if-changed instruction tells Cargo to re-run the build script if the file at the given path has changed.
Currently, Cargo only uses the filesystem last-modified timestamp to determine if the file has changed.
It compares against an internal cached timestamp of when the build script last ran.


After running the build.rs, it generates files in Dart and Rust protobuf files using the same proto files.
Dart:
* `share.pb.dart`
* `event_map.pb.dart`

These files are located in "`packages/flowy_sdk/lib/protobuf/`".

Rust:
* `share.rs`
* `event_map.rs`

These files are located in "`xxx-crate/src/protobuf`".


### Part Five
The class, TextBlockEventExportDocument, is automatically generated in the Dart side using the AST from `Part One`. The function `export_handler` will
get called when the `ExportDocument` event happened. The calling route as the picture shown below.

1. Repository constructs the `TextBlockEventExportDocument` class, and call `send()` function.
2. Front-end's FFI serializes the event and the `ExportPayloadPB` to bytes.
3. The bytes were sent to Back-end.
4. Back-end's FFI deserializes the bytes into the corresponding `event` and `ExportPayloadPB`.
5. The dispatcher sends the `ExportPayloadPB` to the module that registers as the event handler.
6. `ExportPayloadPB` will try to parse into `ExportParams`. It will return an error if there are illegal fields in it.

   For example: the `view_id` field in the `ExportPayloadPB` should not be empty.

7. Module's `export_handler` function gets called with the event and data.
8. At the end, `export_handler` will return 'ExportDataPB', which will be post to the frontend. 

![file : event_map.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/FlowySDK-Protobuf_Communication.svg)

