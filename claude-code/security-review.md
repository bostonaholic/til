# /security-review

`/security-review` is a built-in slash command in Claude Code that performs a
security review of pending changes on the current branch.

## Usage

```sh
/security-review
```

Run this command in your Claude Code session to have Claude analyze your
uncommitted changes for security vulnerabilities.

## What it does

- Examines code modifications not yet committed
- Identifies potential security vulnerabilities (injection flaws, auth issues, etc.)
- Provides recommendations for hardening the code
- Focuses specifically on your pending changes, not the entire codebase

## When to use it

- Before committing sensitive code (authentication, authorization, data handling)
- After implementing API endpoints or form handlers
- When working with user input, database queries, or external services
- As a final check before pushing changes

## Example workflow

```sh
# Make your changes
git status  # verify pending changes

# Run security review in Claude Code
/security-review

# Address any findings, then commit
git add .
git commit -m "Add secure user input handling"
```

💡 This command only reviews uncommitted changes. For a full codebase audit,
use `/security-audit` instead.

🎉 Happy coding!
