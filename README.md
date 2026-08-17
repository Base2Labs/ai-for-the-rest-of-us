# AI for the Rest of Us

A talk on what changed with AI-assisted work, how the agent loop actually works, and how to work with it well — built with [Slidev](https://sli.dev).

Deck source is split per act under `pages/`, imported by `slides.md` via Slidev's `src:` includes so each act can be edited independently.

## Structure

```
slides.md          # front matter + src: imports per act
pages/              # one file per act
snippets/           # real files, transcluded into slides
public/             # diagrams and static assets
artifacts/          # the audience's takeaway — see below
notes/demo-runbook.md
```

## Artifacts

**Start here if you came for the thing you were promised at the end of the talk.**

The deck carries no project links, so [`artifacts/`](./artifacts/) is what there is — a method for using an AI to understand something rather than to avoid understanding it. Neither file assumes you attended, and neither is about programming.

- [`artifacts/meta-learning-technique.md`](./artifacts/meta-learning-technique.md) — the method, and why it is shaped the way it is. Read this first.
- [`artifacts/primer-roadmap-template.md`](./artifacts/primer-roadmap-template.md) — the file you copy. Fill in the blanks, hand it to an assistant, say `begin`.

The short version: most people ask an AI to write a summary and then read it, which produces a document and very little understanding. This does the reverse — you get taught in conversation, quizzed with your answers actually checked, and the write-up comes last, as a byproduct. Advancing is gated on that write-up, so the step that produces the learning is the one you cannot skip.

## Local development

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

Deploys automatically to GitHub Pages on push to `main` via `.github/workflows/deploy.yml`.
