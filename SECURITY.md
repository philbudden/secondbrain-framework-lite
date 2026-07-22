# Security And Privacy

SecondBrain Framework Lite is a plain-Markdown framework. It does not run code, connect to services, inspect folders, or upload anything by itself. The main security and privacy risks come from what a user chooses to place in the vault or upload into an LLM chat.

## Reporting Issues

Please do not report a vulnerability by opening a public issue if the report could expose private notes, credentials, customer data, employee data, confidential work material, screenshots, or private links.

Use the repository's private vulnerability reporting channel where available, or contact the maintainer privately.

## Privacy Boundaries

Do not include real private material in:

- examples;
- screenshots;
- pull requests;
- issues;
- test documents;
- copied chat transcripts.

Use fictional examples that cannot be mistaken for real people, organisations, customers, projects, credentials, or internal systems.

## LLM Chat Safety

This framework assumes the user will deliberately upload selected files into an LLM chat. Before doing that, users should check:

- whether the content is allowed to be shared with the chosen LLM service;
- whether the content includes confidential, regulated, customer, employee, or personal data;
- whether the model provider may retain prompts, uploads, or outputs;
- whether organisational policy permits that use.

If in doubt, do not upload the material. Redact, summarise, or use a safer internal tool instead.

## Scope

Because this project contains no executable tooling, security reports are most likely to concern:

- accidental inclusion of private material;
- unsafe prompt instructions;
- misleading documentation that implies the LLM can access or update files it cannot see;
- provider-specific advice that could lead users to upload material somewhere inappropriate.
