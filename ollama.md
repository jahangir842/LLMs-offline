# What is Ollama

Ollama is an open-source project that serves as a powerful and user-friendly platform for running LLMs on your local machine. It acts as a bridge between the complexities of LLM technology and the desire for an accessible and customizable AI experience.

At its core, Ollama simplifies the process of downloading, installing, and interacting with a wide range of LLMs, empowering users to explore their capabilities without the need for extensive technical expertise or reliance on cloud-based platforms. 

## Usefull links:
**Official Site** https://ollama.com/

**Github Repo** https://github.com/ollama/ollama

**ollama supported models** https://ollama.com/library

**oolama docker image** https://hub.docker.com/r/ollama/ollama

**Article** https://medium.com/@1kg/ollama-what-is-ollama-9f73f3eafa8b

# Installation methods:

## Installation Method 1: ollama-installation on Windows

1. **Download Installer:**
   - Visit the official Ollama website: [https://ollama.com/download](https://ollama.com/download).
   - Download the installer for Windows.

2. **Install Ollama:**
   - Run the downloaded installer.
   - Follow the on-screen instructions to complete the installation.

3. **Verify Installation:**
   - Open a web browser.
   - Navigate to: [http://localhost:11434](http://localhost:11434).
   - Ensure the Ollama service is running and accessible.

---
   
## Installation Method 2: ollama-installation on Linux:


To install Ollama on Ubuntu, you can follow these steps:

1. **Update the Package List:**
   Start by updating your package list to ensure you have the latest information about available packages.
   ```bash
   sudo apt update
   ```

2. **Install Required Dependencies:**
   Ollama may require certain dependencies to be installed. Make sure you have `curl` installed.
   ```bash
   sudo apt install -y curl
   ```

5. **Install Ollama:**
   Now, you can install Ollama using the package manager.
   ```bash
   curl -fsSL https://ollama.com/install.sh | sh
   ```

6. **Verify Installation:**
   After installation, verify that Ollama is installed correctly by checking its version or running it.
   ```bash
   ollama --version
   ```
7. **Verify in Browser**
   
   Open http://localhost:11434

1. **Check Help:**
   To see the available commands and options, you can run:
   ```bash
   ollama --help
   ```

2. **Basic Commands:**
   Here are some common commands you might use to interact with Ollama. Replace `<command>` with the specific command you want to execute.

   ```bash
   ollama <command> [options]
   ```

3. **Example Commands:**
   - **Starting Ollama:**
     ```bash
     ollama start
     ```
   - **Stopping Ollama:**
     ```bash
     ollama stop
     ```
   - **Checking Status:**
     ```bash
     ollama status
     ```

4. **Configuration:**
   You might need to configure Ollama to suit your needs. Configuration files are typically located in `~/.ollama` or `~/.config/ollama`. You can edit these files to change settings.

5. **Using Ollama in a Script:**
   You can integrate Ollama commands into shell scripts to automate tasks. Here’s an example of a simple script to start Ollama:

   ```bash
   #!/bin/bash
   ollama start
   ```

---

# After installation:

you can interact with llm with two methods:
1. Command line
2. Web API On http://localhost:11434

## 1. Run with command line:
Run the required llama model (e.g llama2 or llama3) with following command:

`
ollama run llama3
`
It will start downloading the required model and start terminal to interact with model.

## 2. Run with GUI:

Following GUI options are available

 a. OpenWebUI
 
 b. Text Generation WebUI
 
 c. Pinokio (GUI Installer)
