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
We define the `Event` and the `Protobuf data struct` in Rust, for example, the `FolderEvent` defined in event.rs and `ExportData` defined in share.rs.
They are not only used as the source codes but also used as the material for generating the [proto file](https://developers.google.com/protocol-buffers/docs/proto3).
How to generate the proto file?

We use the [syn](https://docs.rs/syn/latest/syn/) to collect the [AST](https://en.wikipedia.org/wiki/Abstract_syntax_tree) information that will be used to generate
the `proto file`. If you interest in how to collect the information in details, you should check out the [Procedural Macros](https://doc.rust-lang.org/reference/procedural-macros.html).


### Part Two
[Build Scripts](https://doc.rust-lang.org/cargo/reference/build-scripts.html) is the perfect way to do the code generation.
Let's check out some pseudocode.

```Rust
fn main() {
    gen_files(env!("CARGO_PKG_NAME"), "./src/protobuf/proto");
}


fn gen_files(crate_name: &str, proto_file_dir: &str) { 
    // 1. generate the proto files to proto_file_dir
    let _ = gen_protos(crate_name);

    // 2. generate the protobuf files(Dart)
    generate_dart_protobuf_files(crate_name, proto_file_dir, &paths, &file_names, &protoc_bin_path);
    
    // 3. generate the protobuf files(Rust)
    generate_rust_protobuf_files(&protoc_bin_path, &paths, proto_file_dir);
}
```

The build scripts will be run before the crate gets compiled. Thanks to the cargo toolchain, we use `cargo:rerun-if-changed=PATH`
to enable the build.rs will only run if the files were changed.

> [cargo:rerun-if-changed=PATH](https://doc.rust-lang.org/cargo/reference/build-scripts.html#rerun-if-changed)
>
> The rerun-if-changed instruction tells Cargo to re-run the build script if the file at the given path has changed.
Currently, Cargo only uses the filesystem last-modified "mtime" timestamp to determine if the file has changed.
It compares against an internal cached timestamp of when the build script last ran.

### Part Three
After the build.rs, it generates files in Dart and Rust protobuf files using the same proto files.

Dart:
* `share.pb.dart`
* `event_map.pb.dart`

These files are located in "`packages/flowy_sdk/lib/protobuf/`".

Rust:
* `share.rs`
* `event_map.rs`

These files are located in "`the-corresponding-crate/src/protobuf`".


### Part Four
The class, FolderEventExportDocument, is automatically generated in the Dart side using the AST from `Part One`. The function `export_handler` will
get called when the `ExportDocument` event happened. The calling route as the picture shown below.

1. Repository calls `send()` function of `FolderEventExportDocument`.
2. Front-end's FFI serializes the event and the data to bytes.
3. The bytes were sent to Back-end.
4. Back-end's FFI deserializes the bytes into the corresponding event and data.
5. The dispatcher sends the data to the module that can register as the event handler.
6. Module's export_handler function gets called with the event and data.

![file : event_map.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/FlowySDK-Protobuf_Communication.svg)



