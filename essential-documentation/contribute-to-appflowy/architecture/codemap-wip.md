# CodeMap(WIP)

This code map introduces the folder hierarchy of AppFlowy.

1.  **`app_flowy`** : The flutter working directory, includes all the Dart code of AppFlowy.

    1.  **`assets`**:&#x20;

        The directory contains all the resources that AppFlowy uses.

        1. **`fonts`**
        2. **`images`**
        3. **`translations`**
    2. **`lib`**
       1. **`core`**:&#x20;
       2.  **`startup`**:&#x20;

           This directory includes the initialized tasks when the application launched.
       3.  **`user`**:

           &#x20;This directory contains all the use-related components.

           1.  **`application`**

               Defines the tasks the **`user`** is supposed to do. (Shouldn't find any UI code or network code)
           2.  **`presentation`**

               &#x20;Consists of Widgets that are used by the **`user`** and also the state of the Widgets.
       4.  **`workspace`**:&#x20;

           This directory includes the codebase that is used to describe the user workspace.&#x20;

           1.  **`application`**

               Defines the tasks the **`workspace`** is supposed to do. (Shouldn't find any UI code or network code)
           2.  **`presentation`**

               &#x20;Consists of Widgets that are used by the **`workspace`** and also the state of the Widgets.
    3. **`packages`**
       1.  **`flowy_board`**:&#x20;

           This directory contains all the codes that are used to build the BoardView.
       2.  **`flowy_editor`**:

           &#x20;This directory contains all the codes that are used to build the FlowyEditor.
       3.  **`flowy_infra`**:&#x20;

           This directory contains the shared Dart code that is used by AppFlowy. Such as the shared text-style configuration, and theme configuration. etc.
       4.  **`flowy_infra_ui`**:&#x20;

           This directory contains the shard Flutter widget that is used by AppFlowy. You can reuse the widgets here before designing to write a new widget.
       5.  **`flowy_sdk`**:&#x20;

           This directory contains the codes that are used to communicate with the backend. Such as the Dart protobuf class definitions, FFI interface, and the dispatch event definitions.


2.  **`rust-lib`**

    This directory is the backend code base that is written in Rust.

    1.  **`dart-ffi`:**&#x20;

        This crate defines the FFI interfaces that are used to communicate with the frontend.&#x20;
    2.  **`dart-notify`**

        This crate defines how to send a notification from backend to frontend.
    3.  **`flowy-database`**

        This crate contains the SQLite database definition.
    4.  **`flowy-folder`**

        This crate defines each workspace struct. A workspace contains a list of Apps, each App contains a list of Views, and each View can be a TextEditor, Grid, or Board.&#x20;
    5.  **`flowy-grid`**

        This crate handles all the Grid operations, such as creating a grid or deleting a row in a grid.
    6.  **`flowy-text-block`**

        This crate help to save the text editor data to disk.
    7.  **`flowy-user`**

        This crate handles all the user-related operations.
    8.  **`flowy-sdk`**

        This crate is used to initial each crate including resolving their dependencies. It encapsulates all the abilities provided by the other crates.


3. **`scripts`**









