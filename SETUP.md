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

## Day 2 Progress
- **Sample Terraform Module**: Created S3 bucket module in `modules/s3-bucket/`
- **terraform-docs**: Installed and configured
- **Documentation**: Auto-generated README.md for the module
- **Validation**: Added input validation for bucket names and environment

## File Structure
iac-doc-generator/
├── SETUP.md
├── modules/
│   └── s3-bucket/
│       ├── main.tf
│       ├── variables.tf
│       ├── outputs.tf
│       ├── README.md
│       └── .terraform-docs.yml

## Next Steps for Day 3
- Set up n8n workflow to automate terraform-docs generation
- Create GitHub webhook integration
- Test the automation pipeline