# genai_engineering

Notebook-first GenAI engineering sandbox covering:

- GenAI fundamentals (temperature/top-p, limits/penalties, embeddings, streaming)
- LangChain + LCEL patterns (chaining, retrievers, RAG demos)
- Tool invocation patterns (single-tool validation, multi-step chaining)
- Evaluation patterns (DeepEval, bias/safety, automated eval)

## Table of Contents

- [Repo layout](#repo-layout)
- [Prerequisites](#prerequisites)
- [Setup](#setup)
- [Run notebooks](#run-notebooks)
- [Quality (optional)](#quality-optional)
- [Dependency management (uv)](#dependency-management-uv)

## Repo layout

Top-level directories:

- **`genai_fundamentals/`**: parameter tuning + embeddings + streaming basics
- **`langchain/`**: LangChain patterns; includes `langchain/lcel/` demos
- **`tools/`**: tool invocation + chaining notebooks
- **`evaluation/`**: evaluation notebooks (DeepEval + safety/bias checks)
- **`pydantic/`**: pydantic basics/demos used for validation patterns
- **`docs/`**: diagrams and supporting artifacts (HTML)

## Prerequisites

- **Python**: \(>= 3.12\)
- **uv**: installed (`uv --version`)

## Setup

Create the virtual environment and install dependencies:

```bash
uv sync --dev
```

Set environment variables:

```bash
cp .env.example .env
```

Then edit `.env` with real API keys.

> [!IMPORTANT]
> Do not commit `.env`.

## Run notebooks

Launch Jupyter:

```bash
uv run jupyter lab
```

## Quality (optional)

These are lightweight checks to keep Python snippets consistent across notebooks and scripts.

```bash
uv run ruff check .
uv run black --check .
```

## Dependency management (uv)

- **Lock dependencies**:

```bash
uv lock
```

- **Export `requirements.txt` (runtime-only)**:

```bash
uv export --format requirements.txt --output-file requirements.txt --no-hashes --no-dev
```
