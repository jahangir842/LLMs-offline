### What is GGUF and GGML?

**Note:** GGML officially phased out, new format called GGUF

GGUF and GGML are file formats used for storing models for inference, especially in the context of language models like GPT (Generative Pre-trained Transformer). Let’s explore the key differences, pros, and cons of each.

**GGML:**  (GPT-Generated Model Language): Developed by Georgi Gerganov, GGML is a tensor library designed for machine learning, facilitating large models and high performance on various hardware, including Apple Silicon.

**GGUF:**  (GPT-Generated Unified Format), introduced as a successor to GGML (GPT-Generated Model Language), was released on the 21st of August, 2023. This format represents a significant step forward in the field of language model file formats, facilitating enhanced storage and processing of large language models like GPT.

Developed by contributors from the AI community, including Georgi Gerganov, the creator of GGML, GGUF’s creation aligns with the needs of large-scale AI models, though it appears to be an independent effort. Its use in contexts involving Facebook’s (Meta’s) LLaMA (Large Language Model Meta AI) models underscores its importance in the AI landscape.

**GGUP on Hugging Face:** https://huggingface.co/docs/hub/en/gguf
Hugging Face Hub supports all file formats, but has built-in features for GGUF format, a binary format that is optimized for quick loading and saving of models, making it highly efficient for inference purposes. GGUF is designed for use with GGML and other executors. GGUF was developed by @ggerganov who is also the developer of llama.cpp, a popular C/C++ LLM inference framework. Models initially developed in frameworks like PyTorch can be converted to GGUF format for use with those engines.

**Download GGUP type model from Hugging Face:** Search the required model name in hugging face, mentioning the word "GGUP" and download it with required quantanization.
https://huggingface.co/models


Here is an incomplete list of clients and libraries known to support GGUF:

- **llama.cpp**: The source project for GGUF, offering a CLI and a server option.
- **text-generation-webui**: The most widely used web UI with many features and powerful extensions, supporting GPU acceleration.
- **KoboldCpp**: A fully featured web UI with GPU acceleration across all platforms and architectures, especially good for storytelling.
- **GPT4All**: A free and open-source local running GUI supporting Windows, Linux, and macOS with full GPU acceleration.
- **LM Studio**: An easy-to-use and powerful local GUI for Windows and macOS (Silicon), with GPU acceleration. Linux support is available in beta as of 27/11/2023.
- **LoLLMS Web UI**: A great web UI with many interesting and unique features, including a full model library for easy model selection.
- **Faraday.dev**: An attractive and easy-to-use character-based chat GUI for Windows and macOS (both Silicon and Intel), with GPU acceleration.
- **llama-cpp-python**: A Python library with GPU acceleration, LangChain support, and an OpenAI-compatible API server.
- **candle**: A Rust ML framework focused on performance and ease of use, including GPU support.
- **ctransformers**: A Python library with GPU acceleration, LangChain support, and an OpenAI-compatible AI server. Note, as of November 27, 2023, ctransformers has not been updated recently and does not support many recent models.
