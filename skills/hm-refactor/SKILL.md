---
name: hm-refactor
description: Improve code structure, naming, architecture, and reduce technical debt without changing behavior.
license: MIT
compatibility: codex
metadata:
  workflow: refactoring
---

# /hm-refactor — Code Refactoring

You are now in **refactor mode**. Your job is to improve code quality without changing behavior.

## Core Principle

Refactoring should make code easier to understand, modify, and extend. If you can't explain why a change makes the code better, don't make it.

## Before You Refactor

1. **Ensure tests exist** — refactoring without tests is gambling
2. **Understand the code's purpose** — don't optimize for readability over correctness
3. **Define success criteria** — what does "better" mean for this code?
4. **Take small steps** — commit after each improvement

## What You Improve

### Code Structure
- Extract functions that do too much
- Remove dead code
- Simplify complex conditionals
- Replace magic numbers with constants
- Reduce nesting depth

### Naming
- Variables and functions should be self-documenting
- Avoid abbreviations that lose meaning
- Use consistent naming patterns
- Rename if better names emerge during refactoring

### Architecture
- Identify and fix circular dependencies
- Enforce module boundaries
- Reduce coupling between components
- Increase cohesion within modules

### Type Safety
- Replace `any` with proper types
- Add missing type annotations
- Create types for domain concepts
- Use discriminated unions for state

### Performance
- Identify N+1 queries
- Cache expensive operations
- Use appropriate data structures
- Remove unnecessary work

## Red Flags to Fix

- Functions longer than 30 lines
- More than 3 levels of nesting
- More than 4 parameters to a function
- Boolean parameters (flags)
- Comments explaining "why" rather than "what"
- Duplicated code blocks
- God classes or God modules

## Output

For each improvement:
```
Before: [code snippet]
After: [improved code snippet]
Reason: why this is better
Files affected: list
```

At the end:
- Total improvements made
- Files modified
- Test coverage status
- Recommendations for further improvement

## Rules

- Never refactor and add features simultaneously
- Always run tests after refactoring
- If tests break, the refactor failed — revert and try again
- Prefer composition over inheritance
- Keep functions doing one thing well
- If code is hard to read, it needs refactoring
- Document "why" decisions for future maintainers
