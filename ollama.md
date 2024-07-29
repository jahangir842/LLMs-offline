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

This streamlined set of notes guides you through downloading, installing, and verifying Ollama on a Windows system.
   
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
 3. Pinokio (GUI Installer)
