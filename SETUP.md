# 🧠 Local-Sage — Installation & Usage (Public Guide)

Local-Sage is a **local-first AI coding assistant** that runs on your computer and connects to **Ollama**.

No cloud. No API keys. No usage limits.

> This repository is the **public setup guide** + downloads.
> The full source code repository can remain private.

---

##  System Requirements

- Windows 10 / 11
- Minimum 8GB RAM (16GB recommended)
- GPU recommended (RTX 3050+ for balanced and Heavy Models)
- Ollama installed → https://ollama.com

---

## ⬇️ Download Local-Sage (Installer)

Download from **GitHub Releases**:

- Releases page: https://github.com/<github>/<repo>/releases

What you download:
- `Local-sage-Setup-1.0.0.exe` (the installer)

Optional (portable build):
- `Local-Sage-win-unpacked.zip` (a zipped portable folder)


---

## ⚙️ Installation (Windows)

1. Download the `.exe` installer  
2. Run the installer  
3. Launch Local-Sage  

Optional:
- Create desktop shortcut  
- Pin to taskbar  

---

## ⚙️ Local AI Setup (Required)

Local-Sage runs 100% locally using Ollama.

### Step 1 — Install Ollama

Download and install:
https://ollama.com

### Step 2 — Download at least one model

Open a terminal and run:

```bash
# Recommended balanced model
ollama pull qwen2.5

# Best for coding + Fix/Generate
ollama pull qwen2.5-coder:14b

# Fast lightweight option (Explain only)
ollama pull llama3.2:1b
```

### IMPORTANT: No manual model run required

You do **not** need to run `ollama run ...`.
Local-Sage uses Ollama’s local HTTP API at `http://localhost:11434`.

---
## 🧠 Models Available

Local-Sage supports a wide range of local LLMs via Ollama, categorized into three tiers based on performance and hardware requirements.

---

### ⚡ Fast Models (Lightweight)

💡 *Best for quick explanations and low-resource systems*

- Phi-3 Mini (3.8B) — ~2.3 GB  
- Phi-3.5 Mini (3.8B) — ~2.2 GB  
- Gemma 2 (2B) — ~1.6 GB  
- Gemma (2B) — ~1.4 GB  
- TinyLlama (1.1B) — ~638 MB  
- Llama 3.2 (1B / 3B) — ~1.3–2.0 GB  
- Qwen 2.5 (3B) — ~1.9 GB  
- Mistral (7B) — ~4.1 GB  

👉 **Use when:**
- You need fast responses  
- Running on limited hardware  
- Doing simple Explain tasks  

---

### 🧠 Balanced Models (Recommended)

⚖️ *Best balance between performance and quality*

- DeepSeek Coder (6.7B) — ~3.8 GB  
- Qwen2.5 Coder (7B) — ~4.4 GB  
- CodeLlama (7B) — ~3.8 GB  
- Llama 3 / 3.1 (8B) — ~4.7 GB  
- Gemma 2 (9B) — ~5.5 GB  
- Qwen 2.5 (7B) — ~4.4 GB  
- Mistral NeMo (12B) — ~7.1 GB  

👉 **Use when:**
- General coding tasks  
- Medium complexity fixes  
- Better accuracy than fast models  

---

### 🔥 Heavy Models (High Performance)

🚀 *Best results for complex code generation and fixes*

- Qwen2.5 Coder (14B) — ~8.9 GB  
- DeepSeek Coder (33B) — ~18 GB  
- Qwen2.5 Coder (32B) — ~19 GB  
- CodeLlama (13B / 34B) — ~7.4–19 GB  
- Llama 3 / 3.1 (70B) — ~39 GB  
- Mixtral (8x7B) — ~26 GB  
- Gemma 2 (27B) — ~16 GB  

👉 **Use when:**
- Complex bug fixing  
- Multi-file generation  
- Production-level code output  

---

## 🎯 Recommended Mode → Model Mapping

To get the best results, use the following model selection strategy:

| Mode | Minimum | Recommended | Best |
|------|--------|------------|------|
| 🟢 Explain | Fast (1B–3B) | Balanced (7B) | Any |
| 🟡 Fix | Balanced (7B) | Heavy (14B) | Qwen2.5-Coder 14B |
| 🔵 Generate (single file) | Balanced (7B) | Heavy (14B) | Qwen2.5-Coder 14B |
| 🔷 Generate (full project) | Heavy (14B) | Qwen2.5-Coder 14B | DeepSeek-Coder 33B |

---

## 🚀 First Run (Quick Start)

1) Open Local-Sage
2) Top-right should show **Ollama ready**
3) Click **Open Folder** and select your project folder
4) Choose models in Fast/Balanced/Heavy

---

## ✨ What it does

Local-Sage has three modes:

- **Explain** — explains the active file
- **Fix** — shows a diff preview → you click **Keep** to apply
- **Generate** — updates existing files via diff preview → you click **Keep** to apply

Important principle:
> Local-Sage does not modify your code unless you click **Keep**.

---

## ⚠️ Known Limitations (Current)

- `.ipynb` notebooks display as raw JSON (you can still Explain/Fix)
- Folders can be created, but **folder delete is not supported** yet
- Balanced models can be hit-or-miss for strict code generation; Heavy models are the best

---

## 🛠 Troubleshooting

### Ollama not connecting

1) Make sure Ollama is running:

```bash
ollama ps
```

2) If it’s not running:

```bash
ollama serve
```

3) Reopen Local-Sage or click refresh (↻)

### Windows SmartScreen warning

If the installer is unsigned, Windows may show SmartScreen warnings. This is common for indie builds.
