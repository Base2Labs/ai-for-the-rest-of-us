# Metacognition: AI as a Thinking Partner

## Presentation Points

- Use AI to accelerate your *understanding*, not just your output
- Anthropic study (Jan 2026): AI group scored 17% lower on mastery — nearly two letter grades
  - Biggest gap: debugging skills
  - Those who asked conceptual questions retained the most
- Low-value patterns: delegating everything, using AI only to debug
- High-value patterns: asking "why", requesting explanations, then coding independently
- During planning, AI helped accelerate understanding of *what* to build, not just *how*
- **The metacognitive premium:** knowing when to trust AI output and when to verify
- Dunning-Kruger risk: less skilled developers may overestimate their ability to evaluate AI code

## Presenter Notes

This is the slide I'm most passionate about. Metacognition means thinking about your own thinking — and it's the difference between using AI well and using it poorly.

Anthropic published a study in January 2026 — a randomized controlled trial with software developers. The AI-assisted group scored 17% lower on mastery quizzes taken minutes after completing tasks. The biggest gap was in debugging skills. But here's what's interesting: not everyone in the AI group scored poorly. The developers who used AI for conceptual inquiry — asking "why does this work?" and "explain this pattern" — scored as well as the hand-coding group. The ones who just delegated code generation and debugging to the AI learned almost nothing.

They identified distinct patterns. Low-scoring developers either delegated everything to the AI, progressively relied on it more, or used it as a debugging crutch. High-scoring developers asked conceptual questions, requested explanations alongside code, or generated code first then asked follow-up questions to build understanding.

There's a broader point here about what I'd call the metacognitive premium. A developer with strong metacognitive skills knows when to trust AI output and when to verify it. They know when their prompt was ambiguous. They know when they're at the edge of their competence and need to slow down. The Dunning-Kruger effect is especially relevant — less skilled developers may overestimate their ability to evaluate AI-generated code, confidently accepting solutions they don't fully understand. This creates a quality problem that will eventually show up in production.

In my own experience, during the planning phase of building an agentic development workflow, I used AI not just to generate a plan but to deepen my understanding of the problem space. That metacognitive application — using the AI to accelerate my comprehension of what I was building — was critical to the quality of what came out.

References:
- https://www.anthropic.com/research/AI-assistance-coding-skills
- "Claude Code Didn't Just Make Developers Faster — It Has Changed Who Gets Paid" by Chris Dunlop
