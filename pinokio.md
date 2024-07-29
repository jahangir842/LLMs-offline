# Pinokio
Pinokio is a browser that lets you install, run, and programmatically control ANY application, automatically. It is a project that simplifies running large language models (LLMs) on your local machine by providing a user-friendly interface and pre-configured settings. It leverages popular libraries and frameworks like Hugging Face Transformers and PyTorch to make it easier for users to interact with and run various LLMs without needing extensive knowledge of the underlying technologies.

Pinokio is a self-contained platform that lets you install apps in an isolated manner.

**Isolated Environment:** no need to worry about messing up your global system configurations and environments

**Batteries Included:** no need to manually install required programs just to install something (such as ffpeg, node.js, visual studio, conda, python, pip, etc.). Pinokio takes care of it automatically.

### Key Features of Pinokio

1. **Simplified Setup**: Pinokio offers a straightforward setup process, making it accessible to users who may not be familiar with the complexities of installing and configuring LLMs.

2. **Pre-configured Environments**: It provides pre-configured environments for running different LLMs, ensuring optimal performance and compatibility.

3. **User-friendly Interface**: Pinokio includes a user-friendly command-line interface (CLI) to manage and run models easily.

4. **Support for Multiple Models**: It supports various models from the Hugging Face Transformers library and can be extended to support additional models.



## 1. Installation on Windows: 

First, install Pinokio. You can usually do this via pip:

Go to the official website and download it. https://pinokio.computer/

Unzip the downloaded file and you will see a .exe installer file.

Run the installer file.

## 2. Installation on Linux:

For linux, you can download and install directly from the latest release on Github (Scroll down to the bottom of the page for all the binaries):
https://github.com/pinokiocomputer/pinokio/releases/tag/2.1.14

Run the following command to install this downloaded deb file.

```
sudo dpkg -i Pinokio_2.1.14_amd64.deb
```
## After installation:

### Installation Guide for Open-WebUI and Ollama

1. **Open the Application:**
   - After installation, launch the application from the apps shortcut.

2. **Initial Setup:**
   - Select the home directory.
   - Choose and save your preferred theme.

3. **Discover and Install Scripts:**
   - Click on the 'Discover' section to explore various available scripts.
   - Locate and select "Text Generation WebUI" for installation.

4. **Installation Process:**
   - The installation of "Text Generation WebUI" will begin. This may take some time.
   - During the installation, you will be prompted to save the file. Use a name like 'Open-WebUI.git' for saving.

5. **Install Ollama (if not already installed):**
   - If Ollama is not installed on your system, you will be redirected to the Ollama official website.
   - Download and install Ollama from the official website, as it is required for running Open-WebUI.

6. **Continue Open-WebUI Installation:**
   - After successfully installing Ollama, return to the application.
   - Continue and complete the installation of Open-WebUI.

By following these steps, you will have both Ollama and Open-WebUI installed and ready for use.
