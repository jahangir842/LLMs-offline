### This page includes:
1. Installation of ollama
2. Uninstallation of ollama
3. Download and run a model
4. Customize the model

# What is Ollama

Ollama is an open-source project that serves as a powerful and user-friendly platform for running LLMs on your local machine. It acts as a bridge between the complexities of LLM technology and the desire for an accessible and customizable AI experience.

At its core, Ollama simplifies the process of downloading, installing, and interacting with a wide range of LLMs, empowering users to explore their capabilities without the need for extensive technical expertise or reliance on cloud-based platforms. 

## Usefull links:
**Official Site** https://ollama.com/

**Github Repo** https://github.com/ollama/ollama

**ollama supported models** https://ollama.com/library

**oolama docker image** https://hub.docker.com/r/ollama/ollama

**Article** https://medium.com/@1kg/ollama-what-is-ollama-9f73f3eafa8b

**Article** https://medium.com/@sumudithalanz/unlocking-the-power-of-large-language-models-a-guide-to-customization-with-ollama-6c0da1e756d9 

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
   Now, you can install Ollama with following command:
   
   ```bash
   curl -fsSL https://ollama.com/install.sh | sh
   ```

7. **Verify Installation:**
   After installation, verify that Ollama is installed correctly by checking its version or running it.
   ```bash
   ollama --version
   ```
8. **Verify in Browser**
   
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

#### **Available Commands**

**serve**
   - **Description**: Start the Ollama service.
   - **Usage**:
     ```sh
     ollama serve
     ```

**run**
   - **Description**: Run a model.
   - **Usage**:
     ```sh
     ollama run [model_name]
     ```

**Note:** Downloaded models are saved in --> /usr/share/ollama/.ollama/models/blobs


**pull**
   - **Description**: Pull a model from a registry.
   - **Usage**:
     ```sh
     ollama pull [model_name]
     ```

**push**
   - **Description**: Push a model to a registry.
   - **Usage**:
     ```sh
     ollama push [model_name]
     ```

**list**
   - **Description**: List available models.
   - **Usage**:
     ```sh
     ollama list
     ```

**ps**
   - **Description**: List running models.
   - **Usage**:
     ```sh
     ollama ps
     ```

**cp**
   - **Description**: Copy a model.
   - **Usage**:
     ```sh
     ollama cp [source_model] [destination_model]
     ```

**create**
   - **Description**: Create a model from a Modelfile.
   - **Usage**:
     ```sh
     ollama create [modelfile]
     ```

**show**
   - **Description**: Show information for a model.
   - **Usage**:
     ```sh
     ollama show [model_name]
     ```

**rm**
    - **Description**: Remove a model.
    - **Usage**:
      ```sh
      ollama rm [model_name]
      ```
**help**
    - **Description**: Display help information for any command.
    - **Usage**:
      ```sh
      ollama help [command]
      ```

#### **Flags**

- `-h`, `--help`
  - **Description**: Display help information.
  - **Usage**:
    ```sh
    ollama --help
    ```

- `-v`, `--version`
  - **Description**: Show version information.
  - **Usage**:
    ```sh
    ollama --version
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
   
## Customize the Model: 

https://medium.com/@sumudithalanz/unlocking-the-power-of-large-language-models-a-guide-to-customization-with-ollama-6c0da1e756d9

Access the model file to understand its structure and parameters. Use ollama help show to show all the commands.

ollama show phi --modelfile














---

### Uninstall Ollama:
You can follow these general steps. Depending on how the installation script works, you might need to remove the binary and any associated files manually. Here are the typical steps to uninstall a software installed via a script:

1. **Find the Installation Directory:**
   Determine where Ollama was installed. Typically, it might be installed in a directory like `/usr/local/bin` or somewhere in your home directory.

2. **Remove the Binary:**
   Remove the Ollama binary from your system. If it was installed in `/usr/local/bin`, you can use:
   ```bash
   sudo rm /usr/local/bin/ollama
   ```

3. **Remove Configuration Files:**
   If there are any configuration files or directories, you might want to remove them as well. These could be in locations like `~/.config/ollama`, `~/.ollama`, or similar directories. For example:
   ```bash
   rm -rf ~/.config/ollama
   rm -rf ~/.ollama
   ```

4. **Remove Any Additional Files:**
   If there are other directories or files created by the installation script, remove them as well. You can often find these by checking the script or the documentation.

If the installation script provided an uninstallation command, use that instead. If you're unsure about what files were installed, you can check the installation script (`https://ollama.com/install.sh`) for details on what files and directories it creates.

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
