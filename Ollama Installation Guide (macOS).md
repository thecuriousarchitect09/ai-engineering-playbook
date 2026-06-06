# Ollama Installation Guide (macOS)

## Overview

Ollama allows you to run Large Language Models (LLMs) locally on your machine.

With Ollama, you can run models such as:

* Llama 3
* Gemma
* Mistral
* Qwen
* DeepSeek
* Phi

without sending data to external cloud providers.

---

# Prerequisites

Recommended:

* macOS 13+ (Ventura or later)
* Apple Silicon (M1/M2/M3/M4)
* 16 GB RAM or higher
* 20+ GB free disk space

Check your Mac architecture:

```bash
uname -m
```

Expected output:

```text
arm64
```

---

# Install Ollama

## Option 1: Download Installer

Download Ollama from:

https://ollama.com/download

1. Download the macOS version
2. Open the downloaded file
3. Drag Ollama to Applications
4. Launch Ollama

---

## Option 2: Install Using Homebrew

```bash
brew install ollama
```

Verify installation:

```bash
ollama --version
```

---

# Start Ollama

Launch the Ollama service:

```bash
ollama serve
```

You should see output similar to:

```text
Listening on 127.0.0.1:11434
```

---

# Download Your First Model

Example: Llama 3

```bash
ollama pull llama3
```

Run it:

```bash
ollama run llama3
```

---

# Popular Models

## Llama 3

```bash
ollama pull llama3
```

## Gemma

```bash
ollama pull gemma3
```

## Qwen

```bash
ollama pull qwen3
```

## DeepSeek

```bash
ollama pull deepseek-r1
```

## Mistral

```bash
ollama pull mistral
```

---

# List Installed Models

```bash
ollama list
```

Example:

```text
NAME             SIZE
llama3           4.7 GB
qwen3            5.2 GB
deepseek-r1      7.6 GB
```

---

# Remove a Model

```bash
ollama rm llama3
```

---

# Show Model Information

```bash
ollama show llama3
```

---

# Run a Model from Terminal

```bash
ollama run llama3
```

Example:

```text
>>> Explain RAG in simple terms.
```

---

# Run Ollama API

Ollama exposes a local REST API.

Default endpoint:

```text
http://localhost:11434
```

Example:

```bash
curl http://localhost:11434/api/generate \
-d '{
  "model":"llama3",
  "prompt":"What is Agentic AI?"
}'
```

---

# Integrating with Python

Install Python SDK:

```bash
pip install ollama
```

Example:

```python
from ollama import chat

response = chat(
    model="llama3",
    messages=[
        {"role": "user", "content": "Explain AI Agents"}
    ]
)

print(response.message.content)
```

---

# Integrating with LangChain

Install:

```bash
pip install langchain langchain-ollama
```

Example:

```python
from langchain_ollama import ChatOllama

llm = ChatOllama(model="llama3")

response = llm.invoke("Explain MCP")
print(response.content)
```

---

# GUI Applications for Ollama

Popular UI tools:

| Tool        | Description            |
| ----------- | ---------------------- |
| Open WebUI  | ChatGPT-like interface |
| LM Studio   | Local model management |
| AnythingLLM | RAG and document chat  |
| Enchanted   | Native macOS interface |

---

# Update Ollama

Using Homebrew:

```bash
brew upgrade ollama
```

---

# Uninstall Ollama

```bash
brew uninstall ollama
```

Remove downloaded models:

```bash
rm -rf ~/.ollama
```

---

# Troubleshooting

## Check Service Status

```bash
curl http://localhost:11434
```

## Port Already in Use

```bash
lsof -i :11434
```

## View Logs

```bash
ollama serve
```

Watch the console output for errors.

---

# Recommended Starter Setup

| Component  | Recommendation       |
| ---------- | -------------------- |
| Runtime    | Ollama               |
| Model      | Llama 3 or Qwen 3    |
| IDE        | VS Code              |
| UI         | Open WebUI           |
| Framework  | LangChain            |
| Deployment | Vercel + API Backend |

This setup is ideal for learning GenAI, RAG, MCP, AI Agents, and Agentic AI development on a local machine.
