---
applyTo: "**/pt-logos-*/**"
---

# Logos Team Instructions

## GitHub Actions

Logos uses a three-tier deployment workflow:

- **`sandbox.yml`** — runs on pull requests; deploys to sandbox via `osinfra-io/pt-techne-opentofu-workflows`
- **`non-production.yml`** — runs on merge to `main`; deploys to non-production
- **`production.yml`** — runs automatically after non-production succeeds

When modifying workflows, update the Mermaid diagram in `README.md` to reflect the changes.

## Repository Practices

- Local development does not have access to OpenTofu state — plans and applies run exclusively in GitHub Actions.
- For detailed OpenTofu conventions (file structure, module pinning, resource patterns, workspace naming), refer to `.github/skills/opentofu.md`.

## Team Configuration Schema

`teams/example.tfvars` is the canonical schema reference for all team configuration options. **Any time a field is added, removed, or changed in `variables.tofu`, the example.tfvars must be updated to match** — including the field itself, its comment explaining purpose and valid values, and whether it is required or optional.
