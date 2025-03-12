# AppFlowy AI - Ollama

AppFlowy supports local AI functionality through Ollama integration. This document guides you through the setup process to enable AI features in AppFlowy without relying on cloud services.


## Setup Process Overview

The setup involves two main components:

1. Installing and configuring Ollama with required models
2. Installing the AppFlowy AI application

## Install Ollama

Follow the [official installation guide](https://ollama.com/) to set up Ollama on your system. Choose instructions for your operating system:

* **Linux/macOS**: Use the terminal script provided on the website.
* **Windows**: Download and run the `.exe` installer.

Verify the installation by running:

```bash
ollama --version
```

***

### Download Required Models

By default, we use the following models:

* llama3.1
* nomic-embed-text

Run these commands in your terminal to download the models:

```bash
ollama pull llama3.1  
ollama pull nomic-embed-text
```

**Verify the Download**:

Check installed models with:

```bash
ollama list
```

You should see `llama3.1` and `nomic-embed-text` in the output.

***

### Start the Ollama Server

Run the following command to start the Ollama server:

```bash
ollama serve
```

⚠️ **Keep the Server Running**:

* The terminal window where you run `ollama serve` must remain open.
* For production setups, run Ollama as a background service (e.g., use `systemd` on Linux or `nohup ollama serve &`).

***

### Verify the Setup

1. Open a **new terminal window**.
2. Send a test request to confirm the server is responsive:

```bash
curl http://localhost:11434
```

You should receive a JSON response confirming the server is active, e.g., it should include the text "Ollama is running".

3. Run this command to generate a test response from your model:

```bash

curl http://localhost:11434/api/generate -d '{
  "model": "llama3.1",
  "prompt": "Hello, why is the sky blue?"
}'

```

A successful test will return a JSON response containing the generated text.


If you want to use additional models, first download (pull) them and then update the configuration in the settings page of AppFlowy.

<figure><img src="../../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>


For instance, I've already installed the deepseek-r1 model, so I can now use it directly within AppFlowy.

<figure><img src="../../.gitbook/assets/use_deepseek.png" alt=""><figcaption></figcaption></figure>


If you attempt to use a model that hasn't been downloaded, AppFlowy will display a "model not found" message


<figure><img src="../../.gitbook/assets/model_not_found.png" alt=""><figcaption></figcaption></figure>


## Install AppFlowy LAI (Local AI)

### macOS

#### Step 1: Download the Application

1. Visit the [AppFlowy-LocalAI releases page](https://github.com/AppFlowy-IO/AppFlowy-LocalAI/releases).
2. Download the **latest**.

***

#### Step 2: Install

1. Unzip the downloaded file.
2. Drag the **AppFlowy LAI** to your `Applications` folder.
3. Launch **AppFlowy LAI** from your Applications directory.\
   Important: Do not move or delete the AppFlowy LAI application if you plan to continue using local AI features.

***

#### Step 3: Install Application

<figure><img src="../../.gitbook/assets/image (7).png" alt="AppFlowy AI macOS download interface"><figcaption><p>Select the macOS .dmg file from the release assets</p></figcaption></figure>


#### Step 4: Verify Installation

1. Open a **new terminal window**.
2. Run this command to confirm the AI plugin is accessible:

```bash
command -v ollama_ai_plugin  
```

✅ **Expected Output**:

```
/usr/local/bin/ollama_ai_plugin  
```

### Windows

#### Step 1: Download the Application

1. Visit the [AppFlowy-LocalAI releases page](https://github.com/AppFlowy-IO/AppFlowy-LocalAI/releases) to find the latest Windows version.
2. Download the latest release suitable for Windows (typically a `.zip` file).

***

#### Step 2: Extract the Application

1. Locate the downloaded zip file (`AppFlowyLAI.zip`) in your Downloads folder.
2. Right-click the file and select **Extract All** to unzip it to your preferred location.

***

#### Step 3: Launch AppFlowy LAI

1. Navigate to the extracted folder (`AppFlowyLAI`).
2. Double-click the executable file (`AppFlowyLAI.exe`) to launch the application.

*Important:* Do not move or delete the `AppFlowyLAI.exe` file or its containing folder if you intend to keep using local AI features.

***

#### Step 3: Verify Installation

1. Open PowerShell.
2. Verify the installation path of `ollama_ai_plugin.exe`:

```cmd
Get-Command ollama_ai_plugin | Select-Object -ExpandProperty Definition
```

**Expected output:**

```
C:\path\to\AppFlowyLAI\ollama_ai_plugin.exe
```

Ensure the output matches the location of your extracted `AppFlowyLAI.exe`.

