# AppFlowy AI - Ollama


### Install Ollama

Follow the [instruction](https://ollama.com/) on Ollama to install ollama.



By default, we use these models

<figure><img src="../../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>

So you need to download corresponding models by running

```
ollama pull llama3.1
ollama pull nomic-embed-text
```



after install these models, then we can start ollama server by running

```
ollama serve
```





### Install AppFlowy Local AI&#x20;

Go to this [page](https://github.com/AppFlowy-IO/AppFlowy-LocalAI/releases) to download the latest AppFlowy AI application.







# AppFlowy AI - Ollama



## Install Ollama  

Follow the [official installation guide](https://ollama.com/) to set up Ollama on your system. Choose instructions for your operating system:  
- **Linux/macOS**: Use the terminal script provided on the website.  
- **Windows**: Download and run the `.exe` installer.  

Verify the installation by running:  
```bash
ollama --version
```  

---

### Download Required Models  

By default, we use the following models:  
<figure><img src="../../.gitbook/assets/image (94).png" alt=""><figcaption></figcaption></figure>  

Run these commands in your terminal to download the models:  
```bash
ollama pull llama3.1  # General-purpose LLM
ollama pull nomic-embed-text  # Embedding model for semantic tasks
```  

**Verify the Download**:  
Check installed models with:  
```bash
ollama list
```  
You should see `llama3.1` and `nomic-embed-text` in the output.  

---

### Start the Ollama Server  

Run the following command to start the Ollama server:  
```bash
ollama serve
```  

⚠️ **Keep the Server Running**:  
- The terminal window where you run `ollama serve` must remain open.  
- For production setups, run Ollama as a background service (e.g., use `systemd` on Linux or `nohup ollama serve &`).  

---

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


## Install AppFlowy Local AI Application  

### Step 1: Download the Application  
1. Visit the [AppFlowy-LocalAI releases page](https://github.com/AppFlowy-IO/AppFlowy-LocalAI/releases).  
2. Download the **latest**.  

---

### Step 2: Install on macOS  
1. Unzip the downloaded file.  
2. Drag the **AppFlowy AI** to your `Applications` folder.  
3. Launch **AppFlowy AI** from your Applications directory.  
    Important: Do not move or delete the AppFlowy AI application if you plan to continue using local AI features.
---

### Step 3: Install Application

<figure>  
  <img src="../../.gitbook/assets/image (7).png" alt="AppFlowy AI macOS download interface">  
  <figcaption>Select the macOS .dmg file from the release assets</figcaption>  
</figure>  


### Step 4: Verify Installation  

1. Open a **new terminal window**.  
2. Run this command to confirm the AI plugin is accessible:  
```bash  
command -v ollama_ai_plugin  
```  
✅ **Expected Output**:  
```  
/usr/local/bin/ollama_ai_plugin  
```  



## Windows
WIP
