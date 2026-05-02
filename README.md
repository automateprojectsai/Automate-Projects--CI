# Automate-Projects--CI

Shared CI/CD reusable workflows for all Automate Projects repos.

## Reusable Workflows

| Workflow | Consumer | Trigger |
|---|---|---|
| `python-plugin-ci.yml` | Plugin listener/advisor repos | `workflow_call` |
| `web-portal-ci.yml` | Web-Portal | `workflow_call` |
| `docs-ci.yml` | Documentation repos | `workflow_call` |
| `auto-merge-template.yml` | Reference template for plugin repos | Copy into consumer repo |

## Self-CI

The `self-ci.yml` workflow validates this repo's own workflow files on every pull request and push to `main`. It runs two checks:

1. **actionlint** — static analysis of all workflow YAML files for GitHub Actions correctness.
2. **YAML parse check** — confirms every workflow file is valid YAML with a top-level mapping.

This gives branch protection a real status check to gate on, eliminating the need for `--admin` bypass merges.
