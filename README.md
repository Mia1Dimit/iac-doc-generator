# IaC Doc Generator

A starter repository for Infrastructure as Code (IaC) projects using [Terraform](https://www.terraform.io/) with automated documentation generation powered by [terraform-docs](https://terraform-docs.io/). This project is designed to help teams maintain up-to-date documentation for Terraform modules using pre-commit hooks and best practices.

---

## Features

- **Terraform module structure**: Organize your infrastructure code in reusable modules.
- **Automatic documentation**: Uses `terraform-docs` to generate and inject documentation into each module's `README.md`.
- **Pre-commit integration**: Ensures documentation is always up-to-date before every commit.
- **Validation**: Input validation for Terraform variables.
- **Extensible**: Easily add new modules and automate their documentation.

---

## Getting Started

### Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) >= 1.0
- [Git](https://git-scm.com/)
- [pre-commit](https://pre-commit.com/)
- [terraform-docs](https://terraform-docs.io/)

### Setup

1. **Clone the repository**

   ```sh
   git clone https://github.com/Mia1Dimit/iac-doc-generator.git
   cd iac-doc-generator
   ```

2. **Install pre-commit hooks**

   ```sh
   pre-commit install
   pre-commit install-hooks
   ```

3. **Install terraform-docs**

   Follow the [terraform-docs installation guide](https://terraform-docs.io/user-guide/installation/).

---

## Usage

### Working with Modules

- Each Terraform module (e.g., [`modules/s3-bucket`](modules/s3-bucket/README.md)) contains its own `main.tf`, `variables.tf`, `outputs.tf`, and `README.md`.
- Documentation for each module is auto-generated and injected into its `README.md` using `terraform-docs`.

### Making Changes

1. Edit or add Terraform files in a module.
2. When you commit, the pre-commit hook will automatically update the module's documentation.
3. Review the changes to `README.md` before pushing.

### Adding a New Module

1. Create a new folder under `modules/` (e.g., `modules/my-new-module/`).
2. Add your `main.tf`, `variables.tf`, `outputs.tf`, and a `.terraform-docs.yml` (copy from an existing module).
3. **Update `.pre-commit-config.yaml`** to include your new module.  
   For example, add a new hook:
   ```yaml
   - id: terraform-docs-my-new-module
     name: terraform-docs for my-new-module
     entry: terraform-docs markdown table ./modules/my-new-module
     language: system
     pass_filenames: false
   ```
4. Run `terraform-docs` manually or make a commit to trigger the pre-commit hook.
5. The documentation will be generated in the new module's `README.md`.

---

## Automation

- **Pre-commit**: Configured in [.pre-commit-config.yaml](.pre-commit-config.yaml) to run `terraform-docs` on each commit.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Credits

- [terraform-docs](https://terraform-docs.io/) for documentation generation.
- Inspired by best practices in Terraform module development.

---

## Contributing

Contributions are welcome! Please open issues or pull requests for improvements or new modules.

---