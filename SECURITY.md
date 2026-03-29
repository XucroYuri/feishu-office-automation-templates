# Security Policy

## Supported Scope

This repository contains reusable templates and documentation. Security concerns usually relate to:

- unsafe write behavior in templates
- accidental leakage of credentials or tenant-specific information
- instructions that could encourage misuse of office automation tools

## Reporting a Vulnerability

Please do not open a public issue for sensitive security concerns.

Instead:

1. prepare a minimal description of the risk
2. identify the affected file or template
3. contact the repository maintainer privately

## Safe Contribution Rules

- never commit secrets, tokens, or tenant IDs
- avoid hardcoding private URLs
- preserve preview-first behavior for write operations
- clearly mark potentially risky workflows
