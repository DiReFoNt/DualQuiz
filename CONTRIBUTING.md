# Contributing

Rules I follow in this project, even though I work alone. The goal is a readable history and a workflow close to a real team.

## Workflow

1. Pick (or create) an Issue and add it to the `Week N` milestone.
2. Create a branch from `main`.
3. Make small, focused commits.
4. Open a Pull Request, link the Issue (`Closes #12`), and wait for CI to pass.
5. Re-read my own diff on the PR page like a reviewer would.
6. Merge with **squash**, delete the branch, pull `main`.

`main` is always working. No direct commits to `main`.

## Branch names

Format: `type/short-description` in lowercase with hyphens.

```
feat/auth-register
fix/jwt-expiry-check
chore/init-monorepo
docs/readme-setup
```

## Commit messages

I use [Conventional Commits](https://www.conventionalcommits.org/).

Format: `type(scope): description`

- Description is in imperative mood: "add", not "added" or "adds".
- Short (about 70 characters), no period at the end.
- Scope is optional: `api`, `web`, `auth`, `db`, `ci`, etc.

| Type | When to use |
|---|---|
| `feat` | New functionality |
| `fix` | Bug fix |
| `chore` | Tooling, config, dependencies, no production code change |
| `docs` | Documentation only |
| `refactor` | Code change that is neither a fix nor a feature |
| `test` | Adding or changing tests |
| `ci` | CI/CD pipeline changes |

Examples:

```
feat(auth): add register endpoint
fix(auth): return 409 on duplicate email
chore: pin Node version to 24
docs: describe local setup in README
```

Bad examples: `fix`, `wip`, `asdf`, `changes`.

## Pull Requests

- Title follows the same format as a commit message (it becomes the squash commit).
- Description: what changed, why, and how I checked it.
- Link the Issue with `Closes #<number>`.
- One PR, one topic. If a PR touches unrelated things, split it.

## Before opening a PR

- [ ] The app starts locally (`api` and `web`)
- [ ] Lint passes
- [ ] Build passes
- [ ] No secrets, `.env` files, or `node_modules` in the diff
- [ ] New env variables are added to `.env.example`
- [ ] If a technical choice was made, it is written in `DECISIONS.md`

## Issues and board

- One Issue is one task of about 2-4 hours.
- Acceptance criteria are written as checkboxes in the Issue.
- Issues belong to a weekly milestone (`Week 1`, `Week 2`, ...) and live on the Project board: Todo, In progress, Done.