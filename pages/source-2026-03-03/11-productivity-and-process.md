# Productivity & Process: The Bottleneck Has Moved

## Presentation Points

- **Value flows to scarcity** — implementation capacity is no longer scarce
- The bottleneck has shifted:
  - **Upstream** → problem definition, planning, system design
  - **Downstream** → integration, deployment, maintenance
- The new high-value roles: architects, integrators/operators, domain experts
- Code generation is fast — **review is now the bottleneck**
- Right-size PRs for human review
- Open questions:
  - How do we build confidence in agent output to delegate more?
  - Can agents decide which PRs need human eyes?
  - What's the right level of human collaboration?
- Potential new processes: regular design discussions, AI-assisted code reviews, AI testing human understanding

## Presenter Notes

The bottleneck in software development has historically been implementation capacity — there were never enough skilled developers to build everything organizations wanted. That scarcity created premium wages for anyone who could write functional code. AI has changed that equation. When one developer with Claude Code can produce what previously required three, the bottleneck doesn't disappear — it moves.

It shifts upstream to problem definition — can you articulate clearly what should be built? And it shifts downstream to integration and maintenance — can you deploy, monitor, and maintain the avalanche of code that now flies out? The people who can conceive what should be built, and the people who can ensure it works in production, become the new scarce resources.

This means three roles gain value. First, architects and strategic thinkers — freed from implementation details, they can spend 90% of their time on system design instead of 40%. Second, integrators and operators — DevOps, SRE, platform engineers — because code still must be deployed, monitored, and secured, and that requires real-time contextual judgment. Third, domain experts — a nurse who can use AI to build clinical workflow tools captures value that previously went to developers who needed months to understand the clinical context.

In practical terms for our teams: if agents produce code faster and we want humans in the loop, reviewing everything becomes the bottleneck. We need to right-size PRs, invest more in upfront planning, and probably introduce new processes — regular design discussions, AI-assisted code reviews, maybe even AI testing engineers' understanding of the code they're shipping. We don't yet have the patterns to enforce the quality we demand, and figuring that out is the work ahead.
