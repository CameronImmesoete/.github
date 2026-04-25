# Copilot Instructions

When assisting with code in this repository or any CameronImmesoete project:

- Follow existing code style and patterns in the repo
- Use type annotations (Python: mypy strict, TypeScript: strict mode)
- Write tests for new functions and bug fixes
- Use descriptive variable and function names
- Prefer simple, readable code over clever abstractions
- For Python repos: use uv for package management, ruff for linting, mypy for type checking, pytest for testing
- For TypeScript repos: use npm, eslint, prettier, vitest
- Never commit secrets, API keys, tokens, or credentials
- Commit messages: imperative mood, under 72 characters, explain why not what
- Python repos should configure mypy in pyproject.toml. The shared CI workflow runs `mypy .` which requires project-level configuration.
- One PR per task
