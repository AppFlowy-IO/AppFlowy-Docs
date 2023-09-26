# 🗺 CodeMap

This code map introduces the folder hierarchy of AppFlowy. **`appflowy_tauri`** the [tauri](https://tauri.app/) working directory.

## src

Contains all the React source code

### 1. appflowy\_app

1.  components

    > Contains all the `React` components.

    1. grid
    2. board
    3. editor
2.  home

    > Implements the application skeleton that including the sider, header, and footer.

### 2. services

1.  backend:

    > Contains all the backend bridge files that including the auto-generated events,protobuf, and etc.

### 3. assets

## [src-tauri](https://tauri.app/v1/guides/getting-started/setup/html-css-js)

Contains all the Rust source code

1.  Cargo.toml

    > Cargo's manifest file. You can declare Rust crates your app depends on, metadata about your app, and much more. For the full reference see Cargo's Manifest Format.
2.  tauri.conf.json

    > This file lets you configure and customize aspects of your Tauri application from the name of your app to the list of allowed APIs. See [Tauri's API Configuration](https://tauri.app/v1/api/config/) for the full list of supported options and in-depth explanations for each.
3.  src/main.rs

    > This is the entry point to your Rust program and the place where we bootstrap into Tauri.
4.  src/request.rs

    > Defines `invoke_request` function to handle how to send the Event to AppFlowy core
