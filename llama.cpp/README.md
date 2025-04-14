# 🦙 LLaMA.cpp Binary Installation Guide (Ubuntu)

This guide assumes you've downloaded a prebuilt archive like `llama-b5129-bin-ubuntu-x64.zip`.

---

## 📥 1. Download and Extract

Official Site: https://github.com/ggml-org/llama.cpp/releases

## Steps: 

```bash
cd ~/Downloads
wget https://github.com/ggml-org/llama.cpp/releases/download/b5129/llama-b5129-bin-ubuntu-x64.zip
unzip llama-b5129-bin-ubuntu-x64.zip
```

It will extract to: `build/bin/`

---

## 📦 2. Move to a Permanent Location

We recommend using `/opt/llama` for system-wide access.

```bash
sudo mkdir -p /opt/llama
sudo cp -r ~/Downloads/build/bin/* /opt/llama/
```

---

## 🔧 3. Set Up Environment Variables

Add `/opt/llama` to your `PATH` and `LD_LIBRARY_PATH`:

```bash
echo 'export PATH=/opt/llama:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/opt/llama:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc
```

> 💡 This allows both executables and required `.so` libraries to be found by the system.

---

## ✅ 4. Verify Installation

Run any LLaMA binary to test:

```bash
llama-run --help
llama-cli --help
```

---

## 🧹 5. Optional: Clean Up

After verifying it works:

```bash
rm -rf ~/Downloads/build
rm ~/Downloads/llama-b5129-bin-ubuntu-x64.zip
```

---

## 📂 Alternative: User-only Setup

If you don't want `sudo`, use:

```bash
mkdir -p ~/tools/llama
cp -r ~/Downloads/build/bin/* ~/tools/llama
echo 'export PATH=$HOME/tools/llama:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=$HOME/tools/llama:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc
```

---
## Run a LLM Model Using llama.cpp

### Step 1: Install llama.cpp

Ensure you have installed `llama.cpp` correctly as per the instructions:
```bash
git clone https://github.com/ggerganov/llama.cpp
cd llama.cpp
make
```

### Step 2: Download the Model

To download the model, you can use HuggingFace or other supported sources. For example, if you're downloading the `DeepSeek-R1-Distill-Qwen-1.5B-GGUF` model from HuggingFace:

1. Go to the HuggingFace model page: [DeepSeek-R1-Distill-Qwen-1.5B-GGUF](https://huggingface.co/unsloth/DeepSeek-R1-Distill-Qwen-1.5B-GGUF/tree/main).
2. Download the `.gguf` model file.

Alternatively, you can use a script:
```bash
huggingface-cli login  # Login to your HuggingFace account
wget https://huggingface.co/unsloth/DeepSeek-R1-Distill-Qwen-1.5B-GGUF/resolve/main/model.gguf
```

### Step 3: Run the Model with `llama-cli`

Once you have the model (`model.gguf`), you can run it using the `llama-cli` tool. Here's how:

```bash
llama-cli -m model.gguf
```

This will start the model and allow you to interact with it directly.

#### Example Conversation:
```bash
# > hi, who are you?
# Hi there! I'm your helpful assistant! I'm an AI-powered chatbot designed to assist and provide information to users like you. I'm here to help answer your questions, provide guidance, and offer support on a wide range of topics. I'm a friendly and knowledgeable AI, and I'm always happy to help with anything you need. What's on your mind, and how can I assist you today?
#
# > what is 1+1?
# Easy peasy! The answer to 1+1 is... 2!
```

### Step 4: Run in Conversation Mode (Optional)

To run in conversation mode with a custom chat template, you can use the `-cnv` flag and specify a suitable chat template:
```bash
llama-cli -m model.gguf -cnv --chat-template NAME
```
This enables the chat-based functionality.

### Step 5: Run `llama-server` for HTTP Access

If you want to expose the model via a web interface, you can start `llama-server`:

```bash
llama-server -m model.gguf --port 8080
```

Now, you can access a basic web UI at [http://localhost:8080](http://localhost:8080) and use the `/v1/chat/completions` endpoint for chat interactions.

#### Example:
- Start the server on port 8080
- Access the API through `http://localhost:8080/v1/chat/completions`

This can be useful for integrating the model into web apps or for more advanced use cases.

### Step 6: Measure Perplexity (Optional)

To measure the perplexity of the model on a given text, you can use `llama-perplexity`:

```bash
llama-perplexity -m model.gguf -f file.txt
```

### Step 7: Benchmark the Model (Optional)

To benchmark the performance of the model, you can use `llama-bench`:

```bash
llama-bench -m model.gguf
```

This will run the model with various parameters and display its performance metrics, such as throughput (`t/s`).

---

With this setup, you can easily run and interact with your LLM model using the tools provided by `llama.cpp`.
