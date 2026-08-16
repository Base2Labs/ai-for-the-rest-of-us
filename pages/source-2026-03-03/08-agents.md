# Agents: Beyond Autocomplete

## Presentation Points

- **AI-Assisted** — Human drives, AI suggests (autocomplete, inline edits)
- **Agentic** — AI drives, human reviews (autonomous task execution)
- **Key components:**
  - MCP (Model Context Protocol) — Connects agents to external tools and data
  - Skills — Reusable instructions that extend agent capabilities
  - Orchestration — Managing multiple agents, parallel execution
- System prompts embedded in agents significantly affect output quality

## Presenter Notes

There's an important distinction between AI-assisted coding and agentic coding. AI-assisted is what most people are familiar with — Copilot autocomplete, inline suggestions, chat panels where you ask questions. The human is still in the driver's seat, writing code and applying suggestions manually.

Agentic coding flips that. You describe what you want, and the agent goes and does it — reads files, writes code, runs tests, iterates. The human's role shifts to reviewing and steering.

The building blocks of agentic workflows are MCP, skills, and orchestration. MCP — Model Context Protocol — is how agents connect to external tools: your codebase, Jira, Slack, databases. Skills are reusable instruction sets that give an agent specialized knowledge for specific tasks. Orchestration is about managing multiple agents working in parallel — this is where things start to scale.

One thing people overlook: the system prompt baked into each agent tool dramatically affects output. The same LLM will perform very differently in Claude Code vs. the Claude chat interface vs. a Copilot custom agent, because the system prompts shape how it reasons and what it prioritizes. Understanding this matters when choosing your tools.
