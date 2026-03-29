# CLAUDE.md

This file provides guidance to AI assistants (Claude and others) working in this repository.

## Repository Overview

- **Name:** Learning
- **Owner:** peterlwkww-ai
- **Purpose:** Daily expense tracker web app
- **Primary Language(s):** HTML, JavaScript

---

## Codebase Structure

```
Learning/
├── CLAUDE.md          # This file
└── index.html         # Single-page expense tracker app
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
```

Common types: `feat`, `fix`, `docs`, `refactor`, `test`, `chore`

---

## Testing

- No build step required — open `index.html` directly in a browser.
- Manual testing: add/delete expenses, check totals, navigate between days.

---

## Code Style & Conventions

- Single-file architecture: all HTML, CSS, and JS live in `index.html`.
- Data is persisted in `localStorage` under the key `expenses_v1`.
- Keep functions small and single-purpose.
- Sanitize all user input rendered into HTML (use `escHtml`).

---

## Key Conventions for AI Assistants

### What to do

- Read existing code before modifying it.
- Match the style, naming, and patterns already present.
- Make the smallest change that satisfies the request.
- Commit and push to the designated branch after completing a task.

### What NOT to do

- Do not push to `main` without explicit permission.
- Do not add speculative features beyond what was asked.
- Do not create new files unless absolutely necessary.
- Do not skip pre-commit hooks (`--no-verify`).

### Security

- Never commit secrets, API keys, or credentials.
- Sanitize all user input rendered into HTML.
- Follow OWASP Top 10 guidance.

---

## Git Push Retry Policy

If a `git push` fails due to a network error, retry with exponential backoff:

| Attempt | Wait before retry |
|---------|-------------------|
| 1       | 2 s               |
| 2       | 4 s               |
| 3       | 8 s               |
| 4       | 16 s              |
