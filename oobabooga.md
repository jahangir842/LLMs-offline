### Oobabooga: Detailed Notes

#### Overview

Oobabooga is a powerful web-based user interface designed for running large language models (LLMs) such as GPT-3 and similar models. It provides an interactive and user-friendly platform for accessing and utilizing these models, either locally or through various APIs.

#### Repository 

https://github.com/oobabooga/text-generation-webui



#### Key Features

- **User Interface**: Provides a clean and intuitive web-based interface for interacting with LLMs.
- **Support for Multiple LLMs**: Compatible with a variety of LLMs, including GPT-3, Ollama, and other OpenAI-compatible models.
- **Local and Remote Access**: Allows users to run models locally on their own hardware or connect to remote APIs.
- **Customizable Settings**: Offers a range of customizable settings to tweak model performance and behavior.
- **Data Security**: Ensures all user data is stored locally with no external requests, maintaining privacy and confidentiality.

#### Installation



##### Method 1: Quick Start with Docker (Recommended)

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
