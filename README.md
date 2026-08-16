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

The deck has no project links in it, so these are the only things the audience leaves with:

- [`artifacts/primer-roadmap-template.md`](./artifacts/primer-roadmap-template.md) — a generic template for a roadmap-driven learning session with an agent.
- [`artifacts/meta-learning-technique.md`](./artifacts/meta-learning-technique.md) — the technique itself, written as explicit steps.

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
