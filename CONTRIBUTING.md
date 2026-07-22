# Contributing

Thank you for improving SecondBrain Framework Lite.

This project is intentionally lightweight. It should remain usable by someone with only a local folder of Markdown files and access to a normal LLM chat interface.

## Principles

- Keep the framework provider-neutral.
- Do not require agents, scripts, package managers, Python, local automation, shell commands, or direct file editing by an AI system.
- Prefer plain Markdown and clear human instructions.
- Make prompts verbose enough to work in ordinary chat tools, including less capable or less context-aware models.
- Preserve the simple folder structure unless there is a strong reason to change it.
- Keep examples fictional and privacy-safe.

## Before Opening A Pull Request

1. Check that no real Daily Notes, meeting transcripts, personal data, credentials, customer data, employee data, private links, or organisation-specific details are included.
2. Use synthetic examples with clearly fictional names and situations.
3. If you change a skill prompt, make sure it clearly states:
   - required uploaded documents;
   - optional uploaded documents;
   - what to do when an optional document is missing;
   - that the model must not pretend to update documents it has not seen;
   - that updated documents should be returned as complete replacement Markdown documents;
   - that facts, dates, owners, actions, and decisions must not be invented.
4. If you add or rename a skill, update the skill menu in `30 Skills/README.md`.
5. If you change folder usage, update the relevant folder `README.md`.
6. Add a short entry to `CHANGELOG.md`.

## Review Checklist

Before proposing a change, read the modified Markdown as if you were a non-technical user trying the framework for the first time.

Ask:

- Would I know where to put the file?
- Would I know what to upload into chat?
- Would I know what to save afterwards?
- Does the prompt work without hidden tooling?
- Does it avoid provider-specific assumptions?
- Does it protect against invented facts and unsafe document updates?

Prefer focused changes that can be understood and reverted independently.
