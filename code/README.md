# llm-zoomCamp-2026
# Course Assistant AI Agent

An intelligent, narrative-driven course teaching assistant built using the Google GenAI SDK and Gemini. This agent automatically navigates course FAQs, handles search queries, handles typos, and maintains contextual conversation history to assist students with logistics and course topics.

## Features

- **Native Agentic Loop:** Utilizes Gemini's native `chats` abstraction to manage multi-turn conversations and iterative tool execution.
- **Automated Function Calling:** Auto-generates tool schemas directly from Python docstrings and type hints to call external search indices.
- **Error Recovery:** Capable of recognizing low-quality search results or typos (e.g., "Olama" vs "Ollama") and refining search keywords autonomously.
- **Robust Environment Management:** Clean separation of configuration, local virtual environments, and sensitive keys.

## Tech Stack

- **Language:** Python 3.11+
- **LLM Provider:** Google GenAI SDK (Gemini 2.5 Pro / Flash)
- **Dependency Management:** [uv](https://github.com/astral-sh/uv)
- **Interactive Environment:** Jupyter Notebooks

---

## Getting Started

### 1. Prerequisites

Ensure you have `uv` installed on your machine. If you don't have it yet, install it via:

```bash
# macOS/Linux
curl -LsSf [https://astral.sh/uv/install.sh](https://astral.sh/uv/install.sh) | sh

# Windows
powershell -c "irm [https://astral.sh/uv/install.ps1](https://astral.sh/uv/install.ps1) | iex"
```

### 2. Installation & Environment Setup
Clone the repository and sync the dependencies using uv:

```bash
# Navigate to the project directory
cd code

# Install dependencies and create the virtual environment
uv sync
```

### 3. Environment Variables
Create a .env file in the root of your project directory to securely store your API credentials. Do not commit this file to GitHub.

```bash
GEMINI_API_KEY=your_actual_api_key_here
```

```bash
Project Structure
├── .gitignore               # System, cache, and credential exclusion rules
├── pyproject.toml           # Project metadata and dependencies managed by uv
├── uv.lock                  # Explicit dependency locking for reproducibility
├── .env                     # Local environment keys (ignored by Git)
├── rag_helper.py            # Search index implementation and retrieval logic
└── notebook.ipynb           # Interactive exploration and main agent loop implementation
```

To run the interactive notebooks or scripts within the managed environment, use uv run:

# To start the Jupyter Notebook interface cleanly inside the environment
```bash
uv run jupyter notebook
```

### Guardrails & Scope
The assistant is strictly constrained via system instructions to answer questions regarding course logistics and materials using verified FAQ data points. Off-topic queries or queries outside the verified data scope are gracefully deflected to maintain context integrity.
