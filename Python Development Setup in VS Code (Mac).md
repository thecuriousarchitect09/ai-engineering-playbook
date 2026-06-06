# Python Development Setup in VS Code (Mac)

## Prerequisites

* macOS
* Internet connection
* VS Code installed

---

# 1. Install Python

Check whether Python is already installed:

```bash
python3 --version
```

If Python is not installed, install it using Homebrew:

```bash
brew install python
```

Or download it from the official Python website.

Verify installation:

```bash
python3 --version
pip3 --version
```

Expected output:

```text
Python 3.x.x
pip 2x.x.x
```

---

# 2. Install Visual Studio Code

Install VS Code and launch it.

Verify installation:

```bash
code --version
```

If the `code` command is unavailable:

1. Open VS Code
2. Press `Cmd + Shift + P`
3. Run:

```text
Shell Command: Install 'code' command in PATH
```

---

# 3. Install Required VS Code Extensions

Open Extensions (`Cmd + Shift + X`) and install:

### Python

Provides Python language support.

### Pylance

Provides IntelliSense, auto-completion, and type checking.

### Jupyter (Optional)

Useful for notebooks and AI experimentation.

### GitHub Copilot (Optional)

AI-assisted code generation.

---

# 4. Create a New Project

Create a project folder:

```bash
mkdir myproject
cd myproject
```

Open in VS Code:

```bash
code .
```

---

# 5. Create a Virtual Environment

Create a virtual environment:

```bash
python3 -m venv .venv
```

Project structure:

```text
myproject/
├── .venv/
└── main.py
```

---

# 6. Activate Virtual Environment

Activate:

```bash
source .venv/bin/activate
```

You should see:

```text
(.venv)
```

Deactivate when finished:

```bash
deactivate
```

---

# 7. Select Python Interpreter in VS Code

1. Press `Cmd + Shift + P`
2. Search:

```text
Python: Select Interpreter
```

3. Select:

```text
.venv/bin/python
```

---

# 8. Install Dependencies

Example:

```bash
pip install requests pandas numpy
```

Check installed packages:

```bash
pip list
```

---

# 9. Create requirements.txt

Generate dependency file:

```bash
pip freeze > requirements.txt
```

Example:

```text
numpy==2.3.0
pandas==2.3.0
requests==2.32.0
```

Install dependencies later:

```bash
pip install -r requirements.txt
```

---

# 10. Create First Python Program

Create `main.py`

```python
print("Hello Python!")
```

Run:

```bash
python main.py
```

Expected output:

```text
Hello Python!
```

---

# 11. Recommended VS Code Settings

Create:

```text
.vscode/settings.json
```

Add:

```json
{
  "python.defaultInterpreterPath": ".venv/bin/python",
  "editor.formatOnSave": true,
  "python.analysis.autoImportCompletions": true
}
```

---

# 12. Useful Packages for AI Development

Install:

```bash
pip install openai
pip install langchain
pip install langgraph
pip install streamlit
pip install ollama
pip install python-dotenv
```

Generate updated requirements:

```bash
pip freeze > requirements.txt
```

---

# 13. Recommended Project Structure

```text
myproject/
├── .venv/
├── app/
│   ├── main.py
│   ├── agents/
│   ├── tools/
│   └── prompts/
├── requirements.txt
├── .env
└── README.md
```

---

# 14. Verify Everything Works

Create:

```python
import sys

print("Python Version:", sys.version)
print("Environment Ready!")
```

Run:

```bash
python main.py
```

Expected output:

```text
Python Version: 3.x.x
Environment Ready!
```

---

# Common Commands

## Activate Environment

```bash
source .venv/bin/activate
```

## Install Package

```bash
pip install package-name
```

## Save Dependencies

```bash
pip freeze > requirements.txt
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Run Application

```bash
python main.py
```

## Deactivate Environment

```bash
deactivate
```

---

# Next Steps

After completing setup, you can start building:

* Python Applications
* REST APIs with FastAPI
* AI Agents
* LangChain Projects
* LangGraph Workflows
* Ollama-based Local LLM Apps
* Streamlit Dashboards
* MCP Servers and Clients
