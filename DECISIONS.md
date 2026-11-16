# Technical decisions

A log of technical choices that had real alternatives: what I picked, why, and what I lose by it.
Newest entries go at the bottom. I add an entry right after making a decision, not at the end of the week.

## Entry template

```
## YYYY-MM-DD. Title

**Context:** what problem I was solving.
**Options:** what I considered.
**Decision:** what I chose.
**Why:** the reasons, in my own words.
**Trade-offs:** what I lose or risk with this choice.
**Revisit when:** (optional) the moment I will reconsider.
```

---

## 2026-11-11. Monorepo with plain folders

```
**Context:** the project has a NestJS API and a Next.js frontend.
**Options:** two separate repositories; one repository with `apps/api` and `apps/web`; one repository with npm workspaces.
**Decision:** one repository, plain folders, no workspaces.
**Why:** one history, one CI pipeline, one README, and easier to show as a portfolio project.
**Trade-offs:** the apps do not share dependencies or code automatically; each has its own `package.json` and `node_modules`.
**Revisit when:** I need shared code between the API and the frontend (for example, shared types).
```
## 2026-11-11. Node.js 24 LTS

```
**Context:** I need one Node version for local work, CI, Docker and hosting.
**Options:** Node 22, Node 24, Node 26 (all LTS at the time of writing).
**Decision:** Node 24 LTS (24.9 or newer), pinned in `.nvmrc` and the `engines` field.
**Why:** well-tested by libraries and hosting platforms; Nest 12 with Jest needs Node 24.9+; Node 26 became LTS only recently.
**Trade-offs:** not the newest LTS line.
**Revisit when:** hosting and libraries fully support Node 26, or Node 24 approaches end of life.
```

## 2026-11-11. CommonJS + Jest instead of ESM + Vitest

```
**Context:** Nest CLI asks which module system and test runner to use for a new project.
**Options:** ESM with Vitest (the CLI default) or CJS with Jest.
**Decision:** CJS with Jest.
**Why:** more tutorials and answers online for a beginner; fewer problems with the TypeORM CLI and migrations; Jest is common in job listings and already in my experience.
**Trade-offs:** ESM is the newer direction for Nest; I will need to learn it later.
**Revisit when:** the next project, or when most of my dependencies' docs assume ESM.
```
---
