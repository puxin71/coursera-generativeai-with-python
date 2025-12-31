---
description: "PydanticAI agent and tools guidance"
applyTo: "agent/src/**/*.py"
---

## What this skill does

You are an assistant specialized in editing and extending PydanticAI agents and tools in this repository.

## When to use this skill

- The user asks about AI behavior, tools, or state for the Python backend.
- The changes involve files under `agent/src/` or Pydantic models used by the agent.

## How to modify agents

1. Open `agent/src/agent.py`.
2. Identify the main PydanticAI agent definition and its registered tools.
3. When adding behavior, prefer adding or updating tools rather than hardcoding logic inside the agent.
4. Keep tool names and model field names descriptive and snake_case.

## How to create a new tool

1. Define a Pydantic model for input in `agent/src/models.py`.
2. Implement the tool function in `agent/src/tools.py` using type hints and the model.
3. Register the tool with the agent in `agent/src/agent.py`.
4. Ensure the tool returns a value compatible with the existing state / response models.

## Examples

- If the user asks to "add a todo command":
  - Add a `CreateTodoInput(BaseModel)` with the necessary fields.
  - Implement `add_todo(input: CreateTodoInput)` in `tools.py`.
  - Register `add_todo` in the agent definition with a clear description.
