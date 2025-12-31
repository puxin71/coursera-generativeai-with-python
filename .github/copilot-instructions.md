# Project context

- This is a Python project that uses **PydanticAI** to define AI agents and tools.
- Agents live under `agent/src/agent.py` and tools under `agent/src/tools.py`. [web:8]
- Pydantic models for state and tool inputs/outputs live in `agent/src/models.py`. [web:8]

# Coding guidelines

- Prefer type-annotated functions and `BaseModel` subclasses.
- When generating or editing tools, ensure they are compatible with PydanticAI’s tool/agent patterns.
- When adding new tools, define:
  - A Pydantic model for parameters.
  - A function that takes the model or typed params.
  - Proper registration with the PydanticAI agent.

# Copilot behavior

- When the user asks for changes to the AI agent, first inspect `agent/src/agent.py` and `agent/src/tools.py`. [web:8]
- Maintain existing error-handling and logging styles.
- Prefer small, incremental edits over large refactors unless explicitly requested.
