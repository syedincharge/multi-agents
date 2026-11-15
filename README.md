# multi-agents

Experiments in multi-agent systems built on [Deep Agents](https://github.com/langchain-ai/deepagents),
LangGraph and LangChain, with Langfuse tracing and Tavily web search.

## Requirements

- Python 3.15+
- [uv](https://docs.astral.sh/uv/) for dependency management
- A Postgres database (used by the LangGraph checkpointer)

## Setup

```bash
# 1. Install dependencies into a local .venv
uv sync

# 2. Create your local env file and fill in your keys
cp .env.example .env
```

`.env` is gitignored and must never be committed. See `.env.example` for the
variables required and where to get each key.

## Running the notebooks

```bash
uv run jupyter lab
```

In VS Code, open a notebook and select the `.venv` interpreter as the kernel.
`.vscode/settings.json` already points the workspace at `.venv/bin/python`.

## Layout

```
src/multi_agent/
  01_deep_agents/
    deep_agents.ipynb    # research agent: tools, todos, subagent delegation, file workspace
workspace/               # agent run output — gitignored, regenerated per run
```

The `deep_agents.ipynb` notebook walks through:

1. Model and environment setup
2. Langfuse tracing
3. Web search and page extraction tools
4. A basic Deep Agent
5. Subtasks with todos
6. Subagent delegation
7. A filesystem-backed research workspace
