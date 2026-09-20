# Digital Conveniences Repository Governance

Digital Conveniences is an umbrella software company. Repositories are classified by the business outcome they support, while sharing a common engineering and security baseline.

## Repository classes

### 1. Product / SaaS
Software owned and operated by Digital Conveniences and sold or licensed as a service or digital product.

Examples:
- multi-tenant SaaS products;
- commercial APIs;
- subscription platforms;
- mobile/web applications sold directly by Digital Conveniences.

Default ownership model:
- product engineering team;
- platform/infrastructure team for shared runtime concerns;
- security team for identity, secrets, auth, deployment, and security-sensitive paths.

### 2. Client Delivery
Software built for a specific client under a commercial engagement.

Default ownership model:
- the assigned client delivery team;
- Digital Conveniences maintainers for governance;
- security/platform reviewers where deployment, identity, secrets, infrastructure, or shared frameworks are affected.

Client repositories must avoid placing client secrets, production data, or contractual/confidential material in source control unless explicitly approved.

### 3. Games
Games and interactive entertainment products owned by Digital Conveniences.

Default ownership model:
- games engineering team;
- product/gameplay owners for game-specific content;
- platform/security reviewers for backend, commerce, identity, analytics, deployment, or shared infrastructure.

### 4. Shared Platform / Internal Engineering
Reusable frameworks, templates, CI/CD, GitOps, infrastructure definitions, developer tooling, and organization governance.

Default ownership model:
- Digital Conveniences maintainers;
- platform engineering;
- security for security-sensitive changes.

## Standard team model

The target team structure is:

- `@Digital-Conveniences/dc-maintainers` — organization/repository governance and senior maintainers.
- `@Digital-Conveniences/dc-platform` — cloud, DevOps, shared platform, CI/CD, infrastructure.
- `@Digital-Conveniences/dc-security` — security-sensitive code, auth, identity, secrets, policy.
- `@Digital-Conveniences/dc-saas` — SaaS/product engineering.
- `@Digital-Conveniences/dc-client-delivery` — client solution engineering.
- `@Digital-Conveniences/dc-games` — games engineering.

Create/confirm these GitHub teams before activating CODEOWNERS templates that reference them.

## Baseline for every repository

Every repository should have:

1. a clear repository class;
2. a repository-local `.github/CODEOWNERS` copied/adapted from an organization template;
3. branch protection/rulesets appropriate to its risk;
4. required pull-request review for protected branches;
5. secret scanning and Dependabot alerts where supported;
6. dependency update automation using either Renovate or Dependabot;
7. an explicit test/build validation path;
8. repository-specific ADRs or architecture documentation where the solution warrants it;
9. no committed production secrets;
10. corporate Git identity for Digital Conveniences work.

## Corporate Git identity

For Mario Phillip's Digital Conveniences work:

`Mario Phillip <mario.phillip@digitalconveniences.com>`

Personal repositories may use a separate personal identity.

## Dependency automation policy

Use one primary version-update bot per repository:

- **Renovate** is the preferred organization-wide default because it supports reusable organization presets and complex multi-ecosystem repositories.
- **Dependabot** remains supported for repositories that intentionally prefer GitHub-native version updates.

Do not enable overlapping Renovate and Dependabot version-update PRs for the same package ecosystem in the same repository.

Dependabot security alerts/security updates may still be enabled independently through GitHub settings.

## Repository-specific precedence

Repository-local policies, ADRs, CODEOWNERS, contribution guides, and security policies override these defaults when they are stricter or more specific.
