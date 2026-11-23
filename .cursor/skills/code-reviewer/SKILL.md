---
name: code-reviewer
description: Review a diff for correctness, missed edge cases, error handling, naming/clarity, security flags like hardcoded secrets or missing input validation, and test coverage gaps. Use when reviewing a diff, pull request, staged changes, or when the user asks for a code review.
---

# Code review

Review the diff. Do not rewrite the change unless the user asks for a fix.

Check each of these:

- correctness
- missed edge cases
- error handling
- naming/clarity
- security flags like hardcoded secrets or missing input validation
- test coverage gaps

## Output

Output findings as a short bulleted list grouped by severity. Use only these groups, and omit a group that has no findings:

```markdown
## Critical
- `path`: what is wrong and why it matters

## Warning
- `path`: what is wrong and why it matters

## Note
- `path`: what is wrong and why it matters
```

Severity:

- **Critical** — incorrect behavior, security flags like hardcoded secrets or missing input validation, or a broken failure path
- **Warning** — missed edge cases, weak error handling, or test coverage gaps for the changed behavior
- **Note** — naming/clarity issues that do not change behavior

If the diff has no findings, say `No findings.`
