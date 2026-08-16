# Tools & Demos

## Presentation Points

- **CLI-based tools are leading** — Claude Code, Codex
  - Primary interaction is chat → IDE becomes secondary
  - CLI enables parallel agent execution
- **IDE-based tools** — Copilot Custom Agents in VSCode
  - Code is front and center; AI is a sidebar
- **Anti-gravity (Agent Manager UI)**
  - Chat as the primary interface
  - Chat history aids context switching
  - Planning mode generates more deterministic prompts
- **Key insight:** Same LLM, different system prompts = very different results

## Presenter Notes

Let me show you some tools. There's been a shift in where the action is happening. CLI tools like Claude Code and Codex are leading right now because if your primary interaction is chatting with an LLM, you don't really need a full IDE. The IDE's value shifts to reviewing and debugging code, where deep LLM integration isn't as necessary. CLIs also open up parallel execution — you can run multiple agents simultaneously, which is hard to do in a single IDE instance.

[DEMO: Copilot Custom Agents in VSCode] — Notice how code is front and center, with the AI in a sidebar. This works well for AI-assisted workflows where you're still driving.

[DEMO: Anti-gravity Agent Manager UI] — Notice the difference. Chat is the primary interface here. The agent interaction is front and center, not the code. Chat history helps with context switching between tasks. And the planning mode helps you craft prompts that execute with more determinism.

The key takeaway from comparing these tools: the same underlying LLM performs very differently depending on the system prompt embedded in the tool. Claude Code vs. the Claude chat interface vs. a Copilot agent — different system prompts lead to different strengths and behaviors. Choose your tool based on your workflow, not just the model.
