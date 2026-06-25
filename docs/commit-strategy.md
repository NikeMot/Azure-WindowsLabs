# Commit Strategy

### Purpose

This document defines how commits should be made in this repository.

The goal is to keep the history readable, reviewable and safe to revert.

### Commit Principles

Commits should be:

* small
* logical
* complete
* descriptive
* safe to revert where possible

### When to Commit

Commit when one logical unit of work is complete.

Examples:

* creating the initial repository structure
* adding a new topic folder
* adding a lab write-up
* updating a completed lab with evidence
* improving the lab template
* correcting a specific documentation issue

### When Not to Commit

Do not commit when:

* secrets or credentials are present
* screenshots contain sensitive information
* unrelated changes are mixed together
* the change cannot be explained
* the repository is in a broken or confusing state
* book PDFs, EPUBs or copyrighted material are staged

### Commit Message Style

Use short, descriptive messages.

Examples:

```text
Add Windows Server foundations topic
Add Active Directory lab template
Document repository design decision
Complete Windows Server baseline lab
Fix Intune compliance lab wording
```

Avoid vague messages such as:

```text
stuff
update
final
work
changes
```

### Pre-Commit Checklist

Before committing:

1. Run `git status`.
2. Review unstaged changes.
3. Review staged changes with `git diff --staged`.
4. Confirm no secrets are included.
5. Confirm no book files are included.
6. Confirm no private tenant or company data is included.
7. Confirm the commit has one clear purpose.
8. Write a meaningful commit message.

### Branching Rules

Use branches when a change is risky, large, experimental or separate from the current work on `main`.

Create a branch for:

* a new lab or major documentation update
* changes to repository structure
* experimental scripts
* anything that may break or confuse the main repository
* work that should be reviewed before merging

Small documentation fixes can be committed directly to `main` while working alone. In a team or production environment, changes should usually be made on a branch and merged through a pull request.

### Example Branch Names

```text
docs/update-lab-template
lab/windows-server-baseline
lab/ad-dns-gpo-troubleshooting
fix/readme-typos
```

### Production Relevance

In production, commit history is part of the operational audit trail. Small, clear commits make review, rollback, incident investigation and knowledge transfer easier.
