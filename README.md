## LLMs Offline

---
### Useful Sites.

**Huggingface.co** https://huggingface.co/

**lmstudio-community on Huggingface:** https://huggingface.co/lmstudio-community https://huggingface.co/lmstudio-community

**TheBloke on Huggingface:** https://huggingface.co/TheBloke

**Uncensored LLMs** https://jarvislabs.ai/blogs/llm_uncensored

---
 
### What is GGUF and GGML?

**Note:** GGML officially phased out, new format called GGUF

GGUF and GGML are file formats used for storing models for inference, especially in the context of language models like GPT (Generative Pre-trained Transformer). Let’s explore the key differences, pros, and cons of each.

**GGML:**  (GPT-Generated Model Language): Developed by Georgi Gerganov, GGML is a tensor library designed for machine learning, facilitating large models and high performance on various hardware, including Apple Silicon.

**GGUF:**  (GPT-Generated Unified Format), introduced as a successor to GGML (GPT-Generated Model Language), was released on the 21st of August, 2023. This format represents a significant step forward in the field of language model file formats, facilitating enhanced storage and processing of large language models like GPT.

Developed by contributors from the AI community, including Georgi Gerganov, the creator of GGML, GGUF’s creation aligns with the needs of large-scale AI models, though it appears to be an independent effort. Its use in contexts involving Facebook’s (Meta’s) LLaMA (Large Language Model Meta AI) models underscores its importance in the AI landscape.

**GGUP on Hugging Face:** https://huggingface.co/docs/hub/en/gguf
Hugging Face Hub supports all file formats, but has built-in features for GGUF format, a binary format that is optimized for quick loading and saving of models, making it highly efficient for inference purposes. GGUF is designed for use with GGML and other executors. GGUF was developed by @ggerganov who is also the developer of llama.cpp, a popular C/C++ LLM inference framework. Models initially developed in frameworks like PyTorch can be converted to GGUF format for use with those engines.

**Download GGUP type model from Hugging Face:** Search the required model name in hugging face, mentioning the word "GGUP" and download it with required quantanization.

---

🚀 **My Recent Project about Ollama: A Deep Dive into Model Management and Offline Testing** 🚀


I’m excited to share my latest project on working with Ollama, an advanced tool for managing machine learning models. This journey took me through the installation of Ollama on both Linux and Windows systems in an isolated, offline network. From downloading models like ollama3.1, Gemma and mistral in GGUF format from Hugging Face, embedding them into Ollama, to testing them thoroughly using command-line tools as well as through Open WebUI — every step was a meticulous process.


Here’s a glimpse of what the article covers:

- **Installation Process**: Setting up Ollama in an offline environment on Linux and Windows.

- **Model Handling**: Downloading and embedding models, and performing tests.

- **Open WebUI Setup**: Integrating Open WebUI with Ollama in Docker format and running comprehensive tests.


If you're interested in learning more about working with machine learning models in offline scenarios, check out the detailed article below. Dive into the steps and commands that made this project a success!


🔗 [Read the full article here] [[Insert Link](https://www.linkedin.com/pulse/how-deploy-ollama-offline-environment-jahangir--utb0f/)]


#MachineLearning #DataScience #Ollama #ModelManagement #OfflineTesting #Docker #AI #TechProjects #Linux #Windows #HuggingFace #GGUF #WebUI #ModelIntegration
