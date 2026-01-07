---
name: til
description: Write a TIL (Today I Learned) entry following the repository's established style and format
---

# TIL Entry Writer

Write a TIL entry based on the user's input. Follow the established patterns from this repository exactly.

## Input Required

The user provides: **$ARGUMENTS**

This should be a short blurb about something they learned. If the category isn't clear, ask for it.

## File Naming Convention

- **Lowercase with hyphens** for multi-word titles: `data-or-form.md`, `update-ref.md`
- **Underscores for special characters**: `!` becomes `_` (e.g., `swap!` → `returned_from_swap_.md`)
- Place in appropriate category subdirectory (e.g., `git/`, `clojure/`, `rails/`)
- Create new category directory if needed

## Required Format

### Title

- Single `#` heading (H1)
- Use backticks for code elements: `# Using \`git stash\``
- Include special characters naturally: `# Thread -> vs. doto`

### Opening

Start with ONE of these patterns:

- **Context**: "From the documentation of `swap!`..."
- **Problem statement**: "I ran into an issue when..."
- **Direct explanation**: "`git update-ref` is a command that..."
- **Observation**: "Often times when I'm trying to..."

### Body Structure

Use these emoji indicators consistently:

- 💡 **Key insight**: Core concept or important principle
- 😕 **Problem/Confusion**: Shows the issue or misconception (optional, use when showing a problem→solution)

Use sub-headers (`##`) for organization when helpful:

- `## Basic Usage`
- `## Why use this?`
- `## Resources`

### Code Blocks

- Always use fenced code blocks with language specification
- Use `plaintext` for REPL sessions and command outputs
- Use specific language tags: `sql`, `ruby`, `bash`, `sh`, `clojure`, etc.
- Show practical, real-world examples

### Ending

**ALWAYS** end with:

```text
🎉 Happy coding!
```

### Resources Section (Optional)

If referencing external documentation, add:

```markdown
## Resources

- [Link text](URL)
```

## README.md Update

After creating the TIL file, update `README.md`:

1. Find the appropriate category section (or create one if new)
2. Add entry in format: `- [Display Title](category/filename.md)`
3. Escape special characters in paths: `clojure/returned_from_swap\!.md`
4. Categories in README are listed alphabetically
5. If adding a new category, insert it in alphabetical order

## Style Guide

- **Conversational and friendly** tone
- **First-person** where appropriate: "I ran into...", "I learned..."
- **Show the learning process**: confusion → revelation
- **Brief and focused**: One concept per entry
- **Practical**: Include real-world usage examples

## Checklist

1. [ ] Determine category (existing or new)
2. [ ] Create filename (lowercase, hyphens, escape special chars)
3. [ ] Write entry with proper format:
   - H1 title with backticks for code
   - Opening sentence (context/problem/explanation)
   - Body with 💡 insights
   - Code examples with language tags
   - 🎉 Happy coding! ending
4. [ ] Update README.md with new entry link
5. [ ] Verify markdown formatting
