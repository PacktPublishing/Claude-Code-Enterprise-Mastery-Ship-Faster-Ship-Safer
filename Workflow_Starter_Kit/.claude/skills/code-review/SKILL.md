---
name: code-review
description: Reviews staged git changes against CLAUDE.md standards
disable-model-invocation: true
---

# Code Review Skill

Review all staged git changes against the project's CLAUDE.md standards.

## Steps

1. Run `git diff --cached` to get staged changes
2. Read the project's CLAUDE.md file(s) for coding standards
3. For each changed file, check against these standards:
   - TypeScript strict compliance (no `any` types)
   - No `console.log` in production code
   - Try-catch in all route handlers
   - Input validation present
   - No hardcoded secrets or API keys
   - PR title format compliance
   - Test coverage for new functionality
4. Report findings with:
   - File path and line number
   - Severity: CRITICAL / HIGH / MEDIUM / LOW
   - Description of the issue
   - Suggested fix

## Output Format

For each issue found:
```
[SEVERITY] file/path.ts:LINE
  Issue: Description
  Fix: Suggested remediation
```

If no issues found, confirm: "All staged changes comply with CLAUDE.md standards."
