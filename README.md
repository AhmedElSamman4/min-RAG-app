# Mini RAG

A minimal implementation of Retrieval-Augmented Generation (RAG) for question answering. It retrieves relevant documents and uses them as context to generate answers.

## Requirements

- Python 3.11
- [uv](https://docs.astral.sh/uv/) (Python package and environment manager)
- Git
- Visual Studio Code (recommended)
- WSL Ubuntu (recommended for Windows users)

> **Tip:** On Windows, keep the project inside the WSL filesystem (for example `~/projects/min-RAG-app`) instead of `/mnt/c/...`. It is faster and avoids Git and file-watching issues.

## Quick Start

1. **Clone the repository**

   ```bash
   git clone https://github.com/AhmedElSamman4/min-RAG-app.git
   cd min-RAG-app
   ```

2. **Install dependencies**

   ```bash
   uv sync
   ```

   This creates the `.venv` virtual environment, installs the declared dependencies, and uses `uv.lock` to pin exact versions.

3. **Set up environment variables**

   ```bash
   cp .env.example .env
   ```

   Open `.env` and fill in your values (for example, your OpenAI API key).

4. **Verify the setup**

   ```bash
   uv run python --version
   ```

   Expected output: `Python 3.11.x`

> Use `uv run <command>` to run anything inside the project environment without activating it manually.

## Project Structure

```
min-RAG-app/
├── .env.example        # Template for environment variables (safe to commit)
├── .gitignore          # Files Git should ignore
├── .python-version     # Python version used by uv
├── pyproject.toml      # Project metadata and dependencies
├── requirements.txt    # Pinned dependency list (optional, for tools that need it)
├── uv.lock             # Resolved dependency versions
└── README.md
```

Local-only files, never committed:

| Path    | Purpose                                      |
| ------- | -------------------------------------------- |
| `.venv/` | Local virtual environment                    |
| `.env`   | Your real secrets and API keys               |

## Configuration

All settings live in `.env`. Start from the template:

```bash
cp .env.example .env
```

Never commit `.env`. It is listed in `.gitignore`, and you can confirm that with:

```bash
git check-ignore -v .env
```

## Development Workflow

```bash
# Create a feature branch
git switch -c my-feature

# Check what changed before committing
git status --short

# Commit and push
git add <files>
git commit -m "Describe your change"
git push -u origin my-feature
```

Then open a Pull Request on GitHub to merge your branch into `main`.

## Development Environment

| Tool            | Version   |
| --------------- | --------- |
| uv              | 0.12.24   |
| System Python   | 3.14.4    |
| Project Python  | 3.11.17   |

The project runs on Python 3.11 through uv, independently of the system Python.

## Roadmap

- [ ] Document ingestion and chunking
- [ ] Embeddings and vector store
- [ ] Retrieval pipeline
- [ ] Answer generation with an LLM
- [ ] Docker setup

## Notes

- Declare dependencies in `pyproject.toml`; `uv.lock` records the resolved versions.
- Never commit `.venv/` or any file containing secrets.

## Run fastapi server

```bash
uv run uvicorn main:app --reload --host 0.0.0.0 --port 5000
```

## Download the POTSTMAN collection from [/assets/postman_collection.json](/assets/ postman_collection.json) and import it into your Postman to test the API endpoints.


