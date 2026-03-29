# CLAUDE.md

This file provides guidance to AI assistants (Claude and others) working in this repository.

## Repository Overview

**Status:** This is a new, empty repository. Update this section as the project takes shape.

- **Name:** Learning
- **Owner:** peterlwkww-ai
- **Purpose:** _(describe the project goal here)_
- **Primary Language(s):** _(to be determined)_

---

## Codebase Structure

> Update this section as directories and modules are added.

```
Learning/
├── CLAUDE.md          # This file
└── ...                # Add structure as the project grows
```

---

## Development Workflow

### Branching Strategy

- **Main branch:** `main`
- **Feature branches:** `feature/<short-description>`
- **Claude-managed branches:** `claude/<task-slug>`
- Always develop on a dedicated branch; never commit directly to `main`.

### Commit Conventions

Use [Conventional Commits](https://www.conventionalcommits.org/) format:

```
<type>(<scope>): <short summary>

[optional body]
```

Common types: `feat`, `fix`, `docs`, `refactor`, `test`, `chore`

Examples:
```
feat(auth): add JWT login endpoint
fix(parser): handle empty input gracefully
docs: update CLAUDE.md with project structure
```

### Making Changes

1. Checkout or create the designated branch.
2. Make focused, minimal changes — avoid scope creep.
3. Run tests before committing (see **Testing** below).
4. Commit with a descriptive message.
5. Push with `git push -u origin <branch-name>`.

---

## Testing

> Update this section once a test framework is chosen.

- Run all tests: _(command TBD, e.g. `npm test`, `pytest`, `make test`)_
- Tests should pass before every commit.
- Write tests for new features and bug fixes.

---

## Code Style & Conventions

> Update this section with project-specific linting/formatting rules.

- Follow the style enforced by the project's linter/formatter.
- Keep functions small and single-purpose.
- Prefer explicit over implicit; avoid magic numbers and strings.
- Do not add comments that merely restate what the code does.

---

## Key Conventions for AI Assistants

### What to do

- Read existing code before modifying it.
- Match the style, naming, and patterns already present in the file you are editing.
- Make the smallest change that satisfies the request.
- Commit and push to the designated branch after completing a task.
- Keep this file up to date when the project structure changes significantly.

### What NOT to do

- Do not push to `main` without explicit permission.
- Do not add speculative features, extra error handling, or refactors beyond what was asked.
- Do not create new files unless absolutely necessary.
- Do not skip pre-commit hooks (`--no-verify`).
- Do not add docstrings, comments, or type annotations to code you did not change.

### Security

- Never commit secrets, API keys, or credentials.
- Validate all external input at system boundaries; trust internal code.
- Follow OWASP Top 10 guidance when writing web-facing code.

---

## Git Push Retry Policy

If a `git push` fails due to a network error, retry with exponential backoff:

| Attempt | Wait before retry |
|---------|-------------------|
| 1       | 2 s               |
| 2       | 4 s               |
| 3       | 8 s               |
| 4       | 16 s              |

After 4 failed retries, report the error to the user.

---

## Updating This File

Keep CLAUDE.md current whenever:
- New directories, modules, or services are added.
- The test command or framework changes.
- New code-style rules or linter configs are introduced.
- The branching or release strategy is updated.
