# Mini RAG

A minimal implementation of **Retrieval-Augmented Generation (RAG)** for question answering. It retrieves relevant documents and uses them as context to generate answers.

## Requirements

- Python 3.11
- [uv](https://docs.astral.sh/uv/)
- Git
- Visual Studio Code (recommended)
- WSL Ubuntu (recommended for Windows users)

## Installation

### 1. Verify the Installed Tools

Check the installed versions:

```bash
uv --version
python3 --version
git --version
```

Development environment versions:

- **uv:** `0.12.24`
- **System Python:** `3.14.4`
- **Project Python:** `3.11.17`

> **Note:** The project uses Python 3.11 through `uv`, independently of the system Python version.

### 2. Initialize the Project

Navigate to the project directory:

```bash
cd /mnt/c/My_github/min-RAG-app
```

Initialize the project using Python 3.11:

```bash
uv init --python 3.11
```

This initializes the Python project and creates its configuration files.

### 3. Set Up the Virtual Environment

Create the virtual environment and synchronize dependencies:

```bash
uv sync
```

This command creates the `.venv` virtual environment, installs the project and its declared dependencies, and creates or updates `uv.lock`.

Verify the Python version:

```bash
uv run python --version
```

Expected output:

```text
Python 3.11.17
```

Use `uv run` to execute Python commands within the project environment without manually activating it.

### 4. Create a Git Branch

Create and switch to a dedicated branch for the Mini RAG implementation:

```bash
git switch -c mini-rag
```

Verify the current branch:

```bash
git branch --show-current
```

Expected output:

```text
mini-rag
```

> If the branch already exists, use `git switch mini-rag` instead.

### 5. Configure Git

Configure your Git identity before creating commits:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Replace the example values with your own Git name and email address.

Verify the configuration:

```bash
git config --global user.name
git config --global user.email
```

### 6. Configure `.gitignore`

Create a `.gitignore` file in the **project root directory**:

```gitignore
.venv/
.env
__pycache__/
*.py[cod]
dist/
build/
*.egg-info/
```

This prevents Git from tracking the virtual environment, secret environment files, and generated Python files.

> **Important:** Keep `.venv/` on your local machine, but do not commit it to Git.

### 7. Project Structure

The project contains the following important files and directories:

```text
min-RAG-app/
├── .gitignore
├── .python-version
├── pyproject.toml
├── README.md
├── uv.lock
├── src/
│   └── min_rag_app/
│       └── __init__.py
└── .venv/                 # Local virtual environment; not committed
```

| File or directory | Purpose |
|---|---|
| `pyproject.toml` | Project metadata and dependency declarations |
| `uv.lock` | Records resolved dependency versions |
| `.python-version` | Specifies the project's Python version |
| `.gitignore` | Excludes files from Git tracking |
| `src/min_rag_app/` | Contains the Python package source code |
| `.venv/` | Stores the local virtual environment |

### 8. Verify the Environment

Run the following commands from the project root:

```bash
uv sync
uv run python --version
git branch --show-current
git status
```

Confirm that Python 3.11 is selected, the environment synchronizes successfully, and `.venv/` is excluded from Git tracking.

## Notes

- This project uses `uv` instead of Miniconda for Python environment and dependency management.
- Declare project dependencies in `pyproject.toml` and track their resolved versions in `uv.lock`.
- A `requirements.txt` file is not necessary when using `uv`, unless a particular deployment workflow requires it.
- Docker configuration and RAG-specific dependencies will be documented as they are introduced.
- Never commit `.venv/` or files containing secrets, such as `.env`.

## instollation

### install requered packages

```bash
uv sync 
``` 
## setup virtual enviroment variables

```bash
cp .env.example .env
```
setup your .env file , like 'openai api key' value.