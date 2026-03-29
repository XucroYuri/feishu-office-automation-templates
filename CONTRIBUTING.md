# Contributing

## Scope

This repository accepts improvements to reusable office automation templates built on top of `lark-cli`.

## How To Contribute

1. Fork the repository.
2. Create a branch for one focused change.
3. Keep command frontmatter and section names consistent.
4. Preserve the preview-first behavior for write actions.
5. Update both English and Chinese documentation when behavior changes.
6. Open a pull request with a concise summary and example use case.

## Template Guidelines

- Prefer explicit routing rules.
- Prefer read-first, mutate-second workflows.
- Keep examples realistic and short.
- Do not hardcode credentials, tenant-specific IDs, or private URLs.
- Keep Chinese command files idiomatic and concise.

## Review Checklist

- frontmatter is valid
- command name is stable and clear
- process steps are action-oriented
- examples match actual supported capabilities
- bilingual docs stay aligned
