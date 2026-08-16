# Determinism: Making AI Output Predictable

## Presentation Points

- **Planning** — Good plans reduce hallucinations
- **Code Consistency** — Consistent style in → consistent style out
  - Conventions, naming, structure act as implicit prompts
- **Scripting** — Use scripts for repeatable operations
  - Faster, cheaper, and deterministic vs. LLM calls
- **Tools** — GitNexus for enforcing structure

## Presenter Notes

One of the biggest complaints about AI-generated code is inconsistency. But a lot of that comes down to how you set up the work. Planning is the first lever — a detailed plan with clear requirements gives the agent guardrails, reducing hallucinations. Think of a plan as a very structured prompt.

Code consistency is the second lever. If your existing codebase has a consistent style and structure, the AI will follow suit. Conventions, naming patterns, and project structure act as implicit prompts. If your codebase is messy, expect messy output.

The third lever is scripting. Anywhere you can replace an LLM call with a deterministic script, you should. Scripts are faster, cheaper, and produce the same output every time. Tools like GitNexus help enforce structural consistency across repos. The goal is to make the predictable parts of your workflow actually predictable, so the AI can focus on the parts that need creativity.
