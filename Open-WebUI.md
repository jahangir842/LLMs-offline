# Open WebUI (Formerly Ollama WebUI)

Open WebUI is an extensible, feature-rich, and user-friendly self-hosted WebUI designed to operate entirely offline. It supports various LLM runners, including Ollama and OpenAI-compatible APIs.


**Official website of Open WebUI:** https://openwebui.com/

**Docs of Open WebUI:** https://docs.openwebui.com/

**Github page:** https://github.com/open-webui/open-webui

**Installation Blog :** http://anakin.ai/blog/open-webui-ollama/

**Model Builder:** https://openwebui.com/models/

### Video Guide: 
https://www.youtube.com/watch?v=JMhVLoVyt6A

https://www.youtube.com/watch?v=QHuTBksNt_w

By Network Chunk: https://www.youtube.com/watch?v=Wjrdr0NU4Sk


---

### Installation


### Method 1:  Installation with Docker (Recommended)

**Single-User Mode:** To disable login for a single-user setup, set `WEBUI_AUTH` to `False`. This will bypass the login page. Note that you cannot switch between single-user mode and multi-account mode after this change.

**Data Storage in Docker:** When using Docker to install Open WebUI, include the `-v open-webui:/app/backend/data` in your Docker command to ensure your database is properly mounted and prevent any loss of data.

**Default Configuration**

- **If Ollama is on your computer: Option 1 (By Network Chunk)**
- 
  ```bash
  docker run -d --network=host -e OLLAMA_BASE_URL=http://127.0.0.1:11434 -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```
- **If Ollama is on your computer: Option 2 (By Official Guide, not working for me on ubuntu but ok with windows)**
    ```bash
  docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```

- **If Ollama is on a different server:**
  ```bash
  docker run -d -p 3000:8080 -e OLLAMA_BASE_URL=https://example.com -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```

- **Method of Network Chunk:** https://www.youtube.com/watch?v=Wjrdr0NU4Sk
  ```bash
  docker run -d --network=host -e OLLAMA_BASE_URL=http://127.0.0.1:11434 -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main


**With Nvidia GPU Support:**
```bash
docker run -d -p 3000:8080 --gpus all --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:cuda
```

**OpenAI API Usage Only:**
```bash
docker run -d -p 3000:8080 -e OPENAI_API_KEY=your_secret_key -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```

#### Installing Open WebUI with Bundled Ollama Support

**With GPU Support:**
```bash
docker run -d -p 3000:8080 --gpus=all -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
```

**For CPU Only:**
```bash
docker run -d -p 3000:8080 -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
```

After installation, access Open WebUI at `http://localhost:3000`.

#### Using the Dev Branch
**Note:** The `:dev` branch contains the latest unstable features and changes. Use it at your own risk as it may have bugs or incomplete features.
```bash
docker run -d -p 3000:8080 -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:dev
```

---

### Method 2: Installing from Repository

Follow these steps to install and run Open WebUI:

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/open-webui/open-webui.git
   cd open-webui
   ```

2. **Install Dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Application:**

   ```bash
   python app.py
   ```

4. **Access the Web Interface:**

   Open your web browser and go to [http://localhost:5000](http://localhost:5000) to interact with the Open WebUI interface.

This format makes each step clear and easy to follow.

---


### Method 3:  Installation with pip (Beta)

**Python 3.11 is required.**

1. **Install Open WebUI:**
   ```bash
   pip install open-webui
   ```

2. **Start Open WebUI:**
   ```bash
   open-webui serve
   ```

Access Open WebUI at `http://localhost:8080`.

#### Other Installation Methods
Open WebUI offers various installation alternatives, including non-Docker native installation methods, Docker Compose, Kustomize, and Helm. Visit the Open WebUI Documentation or join the Discord community for comprehensive guidance.

### Troubleshooting

If you're facing issues like "Open WebUI: Server Connection Error," see the TROUBLESHOOTING section or join the Open WebUI Discord community.

### Updating

To update your local Docker installation to the latest version:
```bash
docker run --rm --volume /var/run/docker.sock:/var/run/docker.sock containrrr/watchtower --run-once open-webui
```
Replace `open-webui` with your container name if it is different.


### Method 4:  Installation with Pinokio

See the `pinikio.md` file.

### Conclusion
Continue with the full getting started guide to explore all features and settings of Open WebUI. Enjoy! 😄
