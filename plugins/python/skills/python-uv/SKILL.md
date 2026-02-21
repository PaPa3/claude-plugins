---
name: python-uv
description: "Use this skill whenever Python is involved: running scripts, installing packages, managing dependencies, creating projects, or using Python CLI tools. Always prefer uv and uvx over python, python3, pip, pipx, or virtualenv."
version: 1.0.0
---

# Python via uv Skill

Always use `uv` and `uvx` for Python tasks. Never use `python`, `python3`, `pip`, `pipx`, or `virtualenv` directly.

## Core Rules

| Instead of | Use |
|---|---|
| `python script.py` | `uv run script.py` |
| `python3 script.py` | `uv run script.py` |
| `pip install <pkg>` | `uv add <pkg>` |
| `pip install -r requirements.txt` | `uv sync` |
| `pipx run <tool>` | `uvx <tool>` |
| `python -m pytest` | `uv run pytest` |
| `python -m ruff` | `uvx ruff` |
| `virtualenv .venv` | `uv venv` |

## Key Commands

### Running code
```bash
uv run script.py               # run a Python script
uv run python                  # start interactive REPL
uv run -m pytest               # run a module
uv run --with requests script.py   # run with extra package, no install needed
```

### Running tools (no install needed)
```bash
uvx ruff check .               # linting
uvx ruff format .              # formatting
uvx mypy .                     # type checking
uvx pytest                     # testing
uvx black .                    # formatting
uvx <any-pypi-tool> [args]     # any tool from PyPI, ephemeral
```

### Project management
```bash
uv init <name>                 # create new project with pyproject.toml
uv add <package>               # add dependency
uv add --dev <package>         # add dev dependency
uv remove <package>            # remove dependency
uv sync                        # install all dependencies from lockfile
uv lock                        # update lockfile
uv tree                        # show dependency tree
```

### Python versions
```bash
uv python install 3.12         # install a Python version
uv python list                 # list available/installed versions
uv run --python 3.12 script.py # run with specific Python version
```

### Virtual environments (only when needed explicitly)
```bash
uv venv                        # create .venv in current dir
uv venv --python 3.12          # with specific Python version
```

## Workflow Patterns

### Run a one-off script with dependencies
```bash
uv run --with pandas --with requests script.py
```

### Set up a new Python project
```bash
uv init myproject
cd myproject
uv add fastapi uvicorn
uv run main.py
```

### Lint and format existing code
```bash
uvx ruff check --fix .
uvx ruff format .
```

### Run tests
```bash
uv run pytest                  # if pytest is in project deps
uvx pytest                     # if running without project
```

### Check types
```bash
uvx mypy src/
uvx pyright src/
```

## Notes

- `uv run` automatically creates/manages a virtual environment — no manual activation needed
- `uvx` runs tools in isolated ephemeral environments — no installation leftovers
- `uv add` updates `pyproject.toml` and `uv.lock` automatically
- Prefer `uv run pytest` over `uvx pytest` when pytest is already a project dependency
