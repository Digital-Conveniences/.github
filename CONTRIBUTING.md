# Contributing to Digital Conveniences Repositories

Thank you for contributing.

## Identity

For Digital Conveniences work, contributors should use an identifiable Git identity associated with their approved GitHub account. Mario Phillip's corporate author identity is:

`Mario Phillip <mario.phillip@digitalconveniences.com>`

Repository-specific contribution and authoring rules take precedence where present.

## Working model

- Work on a branch rather than directly on the default branch.
- Use pull requests for review and integration.
- Keep changes focused and document architectural or behavioral impact.
- Follow repository-local `AGENTS.md`, `CONTRIBUTING.md`, ADRs, coding standards, and test requirements.
- Do not commit credentials, tokens, private keys, connection-string secrets, or production data.
- Prefer tests alongside behavioral changes.
- Keep generated artifacts and binaries out of source control unless the repository explicitly requires them.

## Pull requests

A pull request should explain:

- what changed;
- why the change is needed;
- how it was validated;
- any migration, security, operational, or compatibility impact.

Repository-specific branch protection and CODEOWNERS requirements remain authoritative.
