# Text generation web UI

A Gradio web UI for Large Language Models.

Its goal is to become the [AUTOMATIC1111/stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui) of text generation.

## Features

* 3 interface modes: default (two columns), notebook, and chat.
* Multiple model backends: [Transformers](https://github.com/huggingface/transformers), [llama.cpp](https://github.com/ggerganov/llama.cpp) (through [llama-cpp-python](https://github.com/abetlen/llama-cpp-python)), [ExLlamaV2](https://github.com/turboderp/exllamav2), [AutoGPTQ](https://github.com/PanQiWei/AutoGPTQ), [AutoAWQ](https://github.com/casper-hansen/AutoAWQ), [TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM).
* Dropdown menu for quickly switching between different models.
* Large number of extensions (built-in and user-contributed), including Coqui TTS for realistic voice outputs, Whisper STT for voice inputs, translation, [multimodal pipelines](https://github.com/oobabooga/text-generation-webui/tree/main/extensions/multimodal), vector databases, Stable Diffusion integration, and a lot more. See [the wiki](https://github.com/oobabooga/text-generation-webui/wiki/07-%E2%80%90-Extensions) and [the extensions directory](https://github.com/oobabooga/text-generation-webui-extensions) for details.
* [Chat with custom characters](https://github.com/oobabooga/text-generation-webui/wiki/03-%E2%80%90-Parameters-Tab#character).
* Precise chat templates for instruction-following models, including Llama-2-chat, Alpaca, Vicuna, Mistral.
* LoRA: train new LoRAs with your own data, load/unload LoRAs on the fly for generation.
* Transformers library integration: load models in 4-bit or 8-bit precision through bitsandbytes, use llama.cpp with transformers samplers (`llamacpp_HF` loader), CPU inference in 32-bit precision using PyTorch.
* OpenAI-compatible API server with Chat and Completions endpoints -- see the [examples](https://github.com/oobabooga/text-generation-webui/wiki/12-%E2%80%90-OpenAI-API#examples).

## How to install

1) Clone or [download](https://github.com/oobabooga/text-generation-webui/archive/refs/heads/main.zip) the repository.
2) Run the `start_linux.sh`, `start_windows.bat`, `start_macos.sh`, or `start_wsl.bat` script depending on your OS.
3) Select your GPU vendor when asked.
4) Once the installation ends, browse to `http://localhost:7860/?__theme=dark`.
5) Have fun!

To restart the web UI in the future, just run the `start_` script again. This script creates an `installer_files` folder where it sets up the project's requirements. In case you need to reinstall the requirements, you can simply delete that folder and start the web UI again.

The script accepts command-line flags. Alternatively, you can edit the `CMD_FLAGS.txt` file with a text editor and add your flags there.

To get updates in the future, run `update_wizard_linux.sh`, `update_wizard_windows.bat`, `update_wizard_macos.sh`, or `update_wizard_wsl.bat`.

<details>
<summary>
Setup details and information about installing manually
</summary>

### One-click-installer

The script uses Miniconda to set up a Conda environment in the `installer_files` folder.

If you ever need to install something manually in the `installer_files` environment, you can launch an interactive shell using the cmd script: `cmd_linux.sh`, `cmd_windows.bat`, `cmd_macos.sh`, or `cmd_wsl.bat`.

* There is no need to run any of those scripts (`start_`, `update_wizard_`, or `cmd_`) as admin/root.
* To install the requirements for extensions, you can use the `extensions_reqs` script for your OS. At the end, this script will install the main requirements for the project to make sure that they take precedence in case of version conflicts.
* For additional instructions about AMD and WSL setup, consult [the documentation](https://github.com/oobabooga/text-generation-webui/wiki).
* For automated installation, you can use the `GPU_CHOICE`, `USE_CUDA118`, `LAUNCH_AFTER_INSTALL`, and `INSTALL_EXTENSIONS` environment variables. For instance: `GPU_CHOICE=A USE_CUDA118=FALSE LAUNCH_AFTER_INSTALL=FALSE INSTALL_EXTENSIONS=TRUE ./start_linux.sh`.

### Method 2: Quick Start with Docker (Recommended)

**Single-User Mode**:
To disable login for a single-user setup, set `WEBUI_AUTH` to `False`. This will bypass the login page. Note that you cannot switch between single-user mode and multi-account mode after this change.

**Data Storage in Docker**:
When using Docker to install Oobabooga, include the `-v oobabooga:/app/backend/data` in your Docker command to ensure your database is properly mounted and prevent any loss of data.

**Default Configuration**

- **If Ollama is on your computer**:
  ```bash
  docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:main
  ```

- **If Ollama is on a different server**:
  ```bash
  docker run -d -p 3000:8080 -e OLLAMA_BASE_URL=https://example.com -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:main
  ```

**With Nvidia GPU Support**:
```bash
docker run -d -p 3000:8080 --gpus all --add-host=host.docker.internal:host-gateway -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:cuda
```

**OpenAI API Usage Only**:
```bash
docker run -d -p 3000:8080 -e OPENAI_API_KEY=your_secret_key -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:main
```

#### Installing Oobabooga with Bundled Ollama Support

**With GPU Support**:
```bash
docker run -d -p 3000:8080 --gpus=all -v ollama:/root/.ollama -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:ollama
```

**For CPU Only**:
```bash
docker run -d -p 3000:8080 -v ollama:/root/.ollama -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:ollama
```

After installation, access Oobabooga at `http://localhost:3000`.

#### Using the Dev Branch

**Note**: The `:dev` branch contains the latest unstable features and changes. Use it at your own risk as it may have bugs or incomplete features.
```bash
docker run -d -p 3000:8080 -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:dev
```



## Downloading models

Models should be placed in the folder `text-generation-webui/models`. They are usually downloaded from [Hugging Face](https://huggingface.co/models?pipeline_tag=text-generation&sort=downloads).

* GGUF models are a single file and should be placed directly into `models`. Example:

```
text-generation-webui
└── models
    └── llama-2-13b-chat.Q4_K_M.gguf
```

* The remaining model types (like 16-bit transformers models and GPTQ models) are made of several files and must be placed in a subfolder. Example:

```
text-generation-webui
├── models
│   ├── lmsys_vicuna-33b-v1.3
│   │   ├── config.json
│   │   ├── generation_config.json
│   │   ├── pytorch_model-00001-of-00007.bin
│   │   ├── pytorch_model-00002-of-00007.bin
│   │   ├── pytorch_model-00003-of-00007.bin
│   │   ├── pytorch_model-00004-of-00007.bin
│   │   ├── pytorch_model-00005-of-00007.bin
│   │   ├── pytorch_model-00006-of-00007.bin
│   │   ├── pytorch_model-00007-of-00007.bin
│   │   ├── pytorch_model.bin.index.json
│   │   ├── special_tokens_map.json
│   │   ├── tokenizer_config.json
│   │   └── tokenizer.model
```

In both cases, you can use the "Model" tab of the UI to download the model from Hugging Face automatically. It is also possible to download it via the command-line with 

```
python download-model.py organization/model
```

Run `python download-model.py --help` to see all the options.




##### Method 3: Quick Start with Docker (Recommended)

- **If Ollama is on your computer**:
  ```bash
  docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:main
  ```

- **If Ollama is on a different server**:
  ```bash
  docker run -d -p 3000:8080 -e OLLAMA_BASE_URL=https://example.com -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:main
  ```

**With Nvidia GPU Support**:
```bash
docker run -d -p 3000:8080 --gpus all --add-host=host.docker.internal:host-gateway -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:cuda
```

**OpenAI API Usage Only**:
```bash
docker run -d -p 3000:8080 -e OPENAI_API_KEY=your_secret_key -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:main
```

#### Installing Oobabooga with Bundled Ollama Support

**With GPU Support**:
```bash
docker run -d -p 3000:8080 --gpus=all -v ollama:/root/.ollama -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:ollama
```

**For CPU Only**:
```bash
docker run -d -p 3000:8080 -v ollama:/root/.ollama -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:ollama
```

After installation, access Oobabooga at `http://localhost:3000`.

#### Using the Dev Branch

**Note**: The `:dev` branch contains the latest unstable features and changes. Use it at your own risk as it may have bugs or incomplete features.
```bash
docker run -d -p 3000:8080 -v oobabooga:/app/backend/data --name oobabooga --restart always ghcr.io/oobabooga/oobabooga:dev
```

# Method 2: Installation with pip (Beta)

**Python 3.11 is required.**

1. **Install Oobabooga**:
   ```bash
   pip install oobabooga
   ```

2. **Start Oobabooga**:
   ```bash
   oobabooga serve
   ```

Access Oobabooga at `http://localhost:8080`.


#### Other Installation Methods

Oobabooga offers various installation alternatives, including non-Docker native installation methods, Docker Compose, Kustomize, and Helm. Visit the Oobabooga Documentation or join the Discord community for comprehensive guidance.

#### Troubleshooting

If you're facing issues like "Oobabooga: Server Connection Error," see the TROUBLESHOOTING section or join the Oobabooga Discord community.

#### Updating

To update your local Docker installation to the latest version:
```bash
docker run --rm --volume /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower --run-once oobabooga
```
Replace `oobabooga` with your container name if it is different.

#### Conclusion

Continue with the full getting started guide to explore all features and settings of Oobabooga. Enjoy! 😄
