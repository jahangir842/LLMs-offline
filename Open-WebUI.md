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

https://www.youtube.com/watch?v=Wjrdr0NU4Sk

---

## Key Features of Open WebUI ⭐

- 🚀 **Effortless Setup**: Install seamlessly using Docker or Kubernetes (kubectl, kustomize or helm) for a hassle-free experience with support for both `:ollama` and `:cuda` tagged images.

- 🤝 **Ollama/OpenAI API Integration**: Effortlessly integrate OpenAI-compatible APIs for versatile conversations alongside Ollama models. Customize the OpenAI API URL to link with **LMStudio, GroqCloud, Mistral, OpenRouter, and more**.

- 🧩 **Pipelines, Open WebUI Plugin Support**: Seamlessly integrate custom logic and Python libraries into Open WebUI using [Pipelines Plugin Framework](https://github.com/open-webui/pipelines). Launch your Pipelines instance, set the OpenAI URL to the Pipelines URL, and explore endless possibilities. [Examples](https://github.com/open-webui/pipelines/tree/main/examples) include **Function Calling**, User **Rate Limiting** to control access, **Usage Monitoring** with tools like Langfuse, **Live Translation with LibreTranslate** for multilingual support, **Toxic Message Filtering** and much more.

- 📱 **Responsive Design**: Enjoy a seamless experience across Desktop PC, Laptop, and Mobile devices.

- 📱 **Progressive Web App (PWA) for Mobile**: Enjoy a native app-like experience on your mobile device with our PWA, providing offline access on localhost and a seamless user interface.

- ✒️🔢 **Full Markdown and LaTeX Support**: Elevate your LLM experience with comprehensive Markdown and LaTeX capabilities for enriched interaction.

- 🎤📹 **Hands-Free Voice/Video Call**: Experience seamless communication with integrated hands-free voice and video call features, allowing for a more dynamic and interactive chat environment.

- 🛠️ **Model Builder**: Easily create Ollama models via the Web UI. Create and add custom characters/agents, customize chat elements, and import models effortlessly through [Open WebUI Community](https://openwebui.com/) integration.

- 🐍 **Native Python Function Calling Tool**: Enhance your LLMs with built-in code editor support in the tools workspace. Bring Your Own Function (BYOF) by simply adding your pure Python functions, enabling seamless integration with LLMs.

- 📚 **Local RAG Integration**: Dive into the future of chat interactions with groundbreaking Retrieval Augmented Generation (RAG) support. This feature seamlessly integrates document interactions into your chat experience. You can load documents directly into the chat or add files to your document library, effortlessly accessing them using the `#` command before a query.

- 🔍 **Web Search for RAG**: Perform web searches using providers like `SearXNG`, `Google PSE`, `Brave Search`, `serpstack`, `serper`, `Serply`, `DuckDuckGo` and `TavilySearch` and inject the results directly into your chat experience.

- 🌐 **Web Browsing Capability**: Seamlessly integrate websites into your chat experience using the `#` command followed by a URL. This feature allows you to incorporate web content directly into your conversations, enhancing the richness and depth of your interactions.

- 🎨 **Image Generation Integration**: Seamlessly incorporate image generation capabilities using options such as AUTOMATIC1111 API or ComfyUI (local), and OpenAI's DALL-E (external), enriching your chat experience with dynamic visual content.

- ⚙️ **Many Models Conversations**: Effortlessly engage with various models simultaneously, harnessing their unique strengths for optimal responses. Enhance your experience by leveraging a diverse set of models in parallel.

- 🔐 **Role-Based Access Control (RBAC)**: Ensure secure access with restricted permissions; only authorized individuals can access your Ollama, and exclusive model creation/pulling rights are reserved for administrators.

- 🌐🌍 **Multilingual Support**: Experience Open WebUI in your preferred language with our internationalization (i18n) support. Join us in expanding our supported languages! We're actively seeking contributors!

- 🌟 **Continuous Updates**: We are committed to improving Open WebUI with regular updates, fixes, and new features.

Want to learn more about Open WebUI's features? Check out our [Open WebUI documentation](https://docs.openwebui.com/features) for a comprehensive overview!

---

### Installation

### Method 1: Installing from Repository

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

### Method 2:  Installation with Docker (Recommended)

**Single-User Mode:** To disable login for a single-user setup, set `WEBUI_AUTH` to `False`. This will bypass the login page. Note that you cannot switch between single-user mode and multi-account mode after this change.

**Data Storage in Docker:** When using Docker to install Open WebUI, include the `-v open-webui:/app/backend/data` in your Docker command to ensure your database is properly mounted and prevent any loss of data.

**Default Configuration**

- **If Ollama is on your computer:**
  ```bash
  docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```

- **If Ollama is on a different server:**
  ```bash
  docker run -d -p 3000:8080 -e OLLAMA_BASE_URL=https://example.com -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
  ```

- **Method of Network Chunk:** https://www.youtube.com/watch?v=Wjrdr0NU4Sk
  ```bash
  docker run -d -p --network=host -e OLLAMA_BASE_URL=http://127.0.0.1:11434 -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main


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
