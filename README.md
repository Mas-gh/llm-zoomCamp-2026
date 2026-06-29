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
