# 🦙 LLaMA.cpp Binary Installation Guide (Ubuntu)

This guide assumes you've downloaded a prebuilt archive like `llama-b5129-bin-ubuntu-x64.zip`.

---

## 📥 1. Download and Extract

Download: https://github.com/ggml-org/llama.cpp/releases

```bash
cd ~/Downloads
unzip llama-b5129-bin-ubuntu-x64.zip
```

It will extract to: `build/bin/`

---

## 📦 2. Move to a Permanent Location

We recommend using `/opt/llama` for system-wide access.

```bash
sudo mkdir -p /opt/llama
sudo cp -r ~/Downloads/build/bin/* /opt/llama/
```

---

## 🔧 3. Set Up Environment Variables

Add `/opt/llama` to your `PATH` and `LD_LIBRARY_PATH`:

```bash
echo 'export PATH=/opt/llama:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/opt/llama:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc
```

> 💡 This allows both executables and required `.so` libraries to be found by the system.

---

## ✅ 4. Verify Installation

Run any LLaMA binary to test:

```bash
llama-run --help
llama-cli --help
```

---

## 🧹 5. Optional: Clean Up

After verifying it works:

```bash
rm -rf ~/Downloads/build
rm ~/Downloads/llama-b5129-bin-ubuntu-x64.zip
```

---

## 📂 Alternative: User-only Setup

If you don't want `sudo`, use:

```bash
mkdir -p ~/tools/llama
cp -r ~/Downloads/build/bin/* ~/tools/llama
echo 'export PATH=$HOME/tools/llama:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=$HOME/tools/llama:$LD_LIBRARY_PATH' >> ~/.bashrc
source ~/.bashrc
```

---
