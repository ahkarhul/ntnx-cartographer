# Security Policy

## Reporting a Vulnerability

If you believe you've found a security vulnerability in this project, please report it through GitHub's **Private Vulnerability Reporting**:

- Go to the [Security tab](../../security) of this repository
- Click **Report a vulnerability**

Private reports are visible only to the repository maintainers and the reporter. Please do **not** open public issues or pull requests for security problems — that would expose details to everyone watching the repo before a fix is available.

## Scope

This project is a single static HTML file (`index.html`) plus its supporting metadata files. There is no server-side component and no network request handling beyond what your browser does when loading the page. Reports of concern include:

- Cross-site scripting (XSS) reachable through the in-browser UI
- Logic in the Terraform code generator that would emit harmful or unexpected HCL
- Supply-chain or workflow security issues in the CI/CD configuration

Reports outside that scope (e.g. issues in the Nutanix Terraform provider itself) belong with the upstream project — please file them at <https://github.com/nutanix/terraform-provider-nutanix>.

## Response

Maintainers will acknowledge a private report and provide an initial assessment within a reasonable time given the project's hobbyist scale. Critical issues will be prioritized; lower-severity issues may be batched into normal release cycles.
