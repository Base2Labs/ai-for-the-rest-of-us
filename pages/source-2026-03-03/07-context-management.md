# Context Management

## Presentation Points

- **Progressive Context Loading** — Load only what's needed; give the LLM knowledge of what *can* be loaded
- **Session Management** — Keep sessions focused on a single task; close and restart when context drifts
- **Context Compression** — What happens at the limit; manual summarization as a strategy
- **Separate Planning from Execution** — Planning context doesn't eat into execution context
- **Break Down Work** — Smaller units of work = better context fit
- **Code Indexers** — Sourcegraph, GitNexus, CodeGraphContext
- **Scripting over MCP** — For performance-critical paths, scripts save tokens and time

## Presenter Notes

Context is probably the most under-appreciated aspect of working with AI. Every token you put in the context window has a cost — in money, in speed, and in the quality of the response. If you dump everything in, the signal gets lost in the noise.

Progressive context loading is the idea that you don't load everything up front. Instead, you give the LLM awareness of what's available and let it request what it needs. For example, when implementing an agentic workflow, you might give it system-level knowledge about your platform but only load the specific module docs when it asks.

Session management matters more than people realize. A long, wandering chat session accumulates stale context and leads to worse output. Keep sessions focused on a single task and start fresh when you shift.

When you approach the context limit, compression kicks in automatically — and it's lossy. A better strategy is manual compression: summarize the important state yourself, carry it forward, and start a new session. Separating planning from execution is key here too — your plan lives outside the execution context, so it doesn't compete for space. Use code indexers like Sourcegraph, GitNexus, and CodeGraphContext to give agents efficient access to your codebase without stuffing the whole thing into context. And in VSCode, keep only tabs open that are related to the current task — the agent picks up on open files as context. Where possible, prefer scripts over MCP calls for performance-critical paths. Scripts are faster and don't consume tokens.
