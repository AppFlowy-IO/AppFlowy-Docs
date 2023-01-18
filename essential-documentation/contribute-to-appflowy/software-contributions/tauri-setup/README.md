# 📡 Tauri  Setup

## Step 1：
Follow the instructions [here](https://tauri.app/v1/guides/getting-started/prerequisites) to install Tauri and then 
clone [AppFlowy](https://github.com/AppFlowy-IO/AppFlowy)

## Step 2：
Open terminal to install the prerequisites

```shell
# AppFlowy use cargo-make to run the scripts
cargo install cargo-make

# install development tools
cd AppFlowy/frontend
cargo make appflowy-tauri-deps-tools

cd appflowy_tauri
npm install
```

## Step 3：
Open the **[frontend](https://github.com/AppFlowy-IO/AppFlowy/tree/main/frontend)** folder located at xx/AppFlowy/fronted with VSCode.
If you don't have VSCode then back to your terminal.

```shell
cd frontend
cargo make tauri_dev
```

