# Repository Folder Structure

This repository separates learning material, executable examples, notebooks, and automation so each type of content has a clear home.

## Current Layout

```text
agentic-development/
|-- .github/
|   `-- workflows/
|       |-- ci-documentation.yml
|       |-- ci-python.yml
|       |-- ci-repository.yml
|       `-- ci-workflows.yml
|-- .vscode/
|   `-- settings.json
|-- docs/
|   |-- images/
|   `-- 01-folder-structure.md
|-- notebooks/
|-- scripts/
|   |-- ps/
|   `-- py/
|-- src/
|-- .gitignore
|-- .python-version
|-- LICENSE
|-- pyproject.toml
|-- README.md
`-- uv.lock
```

Empty directories contain a `.gitkeep` file so Git can preserve the intended layout until content is added.

## Directory Responsibilities

| Path | Purpose |
| --- | --- |
| `.github/workflows/` | GitHub Actions workflows for repository validation and continuous integration. |
| `.vscode/` | Shared VS Code workspace settings that are safe to commit. |
| `docs/` | Structured notes, guides, architecture decisions, and learning material. |
| `docs/images/` | Images referenced by documentation. |
| `notebooks/` | Jupyter notebooks for exploration, demonstrations, and experiments. |
| `scripts/py/` | Python utilities for repeatable repository tasks and automation. |
| `scripts/ps/` | PowerShell utilities for Windows setup and repository automation. |
| `src/` | Reusable Python modules and executable agent implementations. |

## Root Files

| File | Purpose |
| --- | --- |
| `.gitignore` | Excludes local, generated, secret, cache, and build files from version control. |
| `.python-version` | Selects Python 3.12 for compatible version managers. |
| `LICENSE` | Defines the repository license. |
| `pyproject.toml` | Declares project metadata, the supported Python version, and dependencies. |
| `README.md` | Introduces the repository, roadmap, and learning goals. |
| `uv.lock` | Locks Python dependencies for reproducible environments. |

## Where Content Belongs

- Put conceptual explanations and durable learning notes in `docs/`.
- Put images used by documentation in `docs/images/` and reference them with relative paths.
- Put exploratory code and visual experiments in `notebooks/`.
- Move reusable logic out of notebooks and into `src/`.
- Put repeatable maintenance or setup commands in `scripts/py/` or `scripts/ps/`.
- Keep generated output, credentials, virtual environments, and machine-specific files out of the repository.

## Naming Conventions

- Use lowercase kebab-case for documentation and notebook names, such as `02-agent-loop.md`.
- Use lowercase snake_case for Python modules and scripts, such as `tool_registry.py`.
- Prefix ordered learning documents with two digits so their sequence is clear.
- Choose names that describe one topic or responsibility.

## Continuous Integration

The workflows in `.github/workflows/` keep this structure maintainable:

| Workflow | Validation |
| --- | --- |
| `ci-documentation.yml` | Lints Markdown and checks links. |
| `ci-python.yml` | Checks Python syntax and validates notebook JSON. |
| `ci-repository.yml` | Confirms that required files and directories exist. |
| `ci-workflows.yml` | Lints GitHub Actions workflow definitions. |

When the repository gains tests or additional tooling, extend the existing structure only when the new content has a distinct responsibility. Update this document and the repository-structure workflow together when required paths change.
