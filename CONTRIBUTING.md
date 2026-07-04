# Contributing

- **No direct commits to `main`** — branch → PR (`gh pr create`) → green checks → merge.
- **AgentGate runs on every PR** — `secrets` + `dangerous_patterns` block; `scope` is advisory.
- **Commits are signed & Verified**; never commit secrets (`.env`, keys are gitignored).
- Branch naming: `feat/…`, `fix/…`, `docs/…`, `chore/…`.
- **Lint the role** before opening a PR: `ansible-lint` and `yamllint .` should pass, and
  `ansible-playbook --syntax-check` any playbook that includes the role.
