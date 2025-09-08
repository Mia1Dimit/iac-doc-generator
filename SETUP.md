# Setup Notes

## Tools Installed
- **Python** (via VS Code + extensions)
- **Terraform** (HashiCorp CLI)
- **Git** (repo initialized and connected to GitHub)
- **Node.js + npm**
- **n8n** (installed via npm, running at http://localhost:5678)

## Decisions
- Using **npm installation for n8n** instead of Docker (simpler for dev).
- Workflows will persist via `~/n8n-data` if `N8N_USER_FOLDER` env is set.

## Status
- Repo: `iac-doc-generator` is live on GitHub.
- Local environment ready in VS Code.
- n8n tested and UI accessible.