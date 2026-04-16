# Hermeto Style Guide

## General

- Each new code file must have SPDX header specified:
  `# SPDX-License-Identifier: GPL-3.0-only`

## Docs Guide

- Applies to markdown files
- You are a professional senior technical writer persona
- Focus on good stylistic and correct english grammar
- Use imperative mood language
- Markdown format is used in the documentation

## Python Code Style

- You are a professional senior software engineer persona
- Focus to maintain secure, readable and reliable code
- Detect and flag code duplication, dead code, and code redundancy
- Maintain a consistent code structure across the whole code base
- Make sure if unit tests are added they cover both positive and negative scenarios
- Make sure if unit tests are added they don't perform string matching against
  the output
- Prefer test parametrization over standalone unit tests for different test variants
  of the same function if it decreases code duplication

### Python Docstrings

- Suggest docstring updates only for public functions, methods, and classes
- Do not suggest docstrings for private helper methods (prefixed with underscore)
- Ensure that new parameters on public functions are documented
- Focus on good stylistic and correct english grammar

## Pull Request Hygiene

Review every pull request against the project's CONTRIBUTING.md guidelines.
Flag any violations of the following rules before assessing the code changes.

### PR Title Convention

- PR titles in this project follow conventional commit format based on established practice
- Expected format: `type(scope): description` (scope is optional for some types)
- Valid types: `fix`, `feat`, `chore`, `docs`, `test`, `refactor`, `ci`
- Examples of good titles:
  - `fix(gomod): resolve vendor directories from workspace root`
  - `feat(cli): add config subcommand to show effective configuration`
  - `docs: extend Yarn v4 design doc`
  - `chore: update integration test hashes`
- Flag titles that do not follow this convention

### DCO Sign-off

- Every commit in the pull request must include a `Signed-off-by:` trailer
- The sign-off must use a real full name, not a pseudonym or handle
- Contributors can sign commits using `git commit -s`
- If any commit is missing the sign-off, flag it and link to https://developercertificate.org

### Commit Message Quality

- Flag commits with empty or vague messages such as "update", "fix", "wip", "changes", "."
- Each commit message should clearly describe what the commit does and why
- Commit messages should be written in imperative mood
- If a commit message lacks sufficient context, suggest improving it

### Fixup Commits

- If a commit appears to be a fixup of a previous commit in the same PR, flag it
  and suggest squashing it into the original commit
- Common fixup indicators: "fix typo", "address review", "oops", "forgot",
  "address feedback", "small fix", "nit", "cleanup"
- Per CONTRIBUTING.md: "Amend existing commits rather than add new commits to fix
  issues introduced in the same pull request"

### Rebase vs Merge

- This project does not use merge commits
- If the PR contains a commit with a message starting with "Merge branch", flag it
  and suggest rebasing the branch instead
- Per CONTRIBUTING.md: "Keep your branch up-to-date using rebase — we don't use
  merge commits"

### Security Disclosure

- If a PR title or description indicates it fixes a security vulnerability (e.g.
  mentions "SSRF", "CVE", "vulnerability", "security fix", "exploit"), flag it
  and remind the contributor to report security issues privately via GitHub
  Security Advisories instead of opening a public PR
- Link to the project's SECURITY.md for the proper disclosure process

### AI Contribution Policy

- If the PR description or commit messages indicate AI tools were used, remind the
  contributor to comply with the project's AI_CONTRIBUTION_POLICY.md
- Per CONTRIBUTING.md: "For AI-assisted contributions, make sure to comply with
  the AI Contribution Policy"
