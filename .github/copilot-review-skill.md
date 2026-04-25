# Code Review Standards

Use these criteria when reviewing pull requests across CameronImmesoete repositories.

## Review Dimensions

### 1. Correctness
- Does the code do what the PR description claims?
- Are edge cases handled (zero, negative, null, empty, boundary values)?
- Are error paths tested, not just the happy path?
- Do mathematical calculations match the documented formulas?

### 2. Security
- No secrets, tokens, or credentials in code, config, or comments
- Input validation at system boundaries (user input, file uploads, API responses)
- Dependencies are pinned to specific versions
- No command injection, path traversal, or XSS vectors

### 3. Test Coverage
- New functions have unit tests covering happy path and edge cases
- Bug fixes include a regression test that fails without the fix
- Tests are deterministic (no flaky assertions, no timing dependencies)
- Test names describe the behavior being verified

### 4. Code Quality
- Functions do one thing and are named for what they do
- Variable names are descriptive (not `x`, `temp`, `data2`, `result`)
- No dead code, no commented-out blocks, no unreachable branches
- No copy-paste duplication across functions
- Type annotations present where the language supports them

### 5. Performance
- No O(n^2) loops on unbounded input
- Large files or datasets handled with streaming, not full memory load
- No unnecessary network calls or filesystem I/O in hot paths
- Database queries are indexed and bounded

### 6. Documentation
- Public APIs and exported functions have docstrings or JSDoc
- Complex logic has inline comments explaining the reasoning (not restating the code)
- README updated if user-facing behavior changes
- No TODOs without a tracking reference (issue number or owner)

### 7. Regression Risk
- What existing behavior could this change break?
- Are downstream consumers or dependents considered?
- Is there a clear rollback path if problems surface after merge?
- Were before/after behaviors verified for affected workflows?

## Review Output Format

For each issue found, include:
- **Severity:** Critical / High / Medium / Low
- **Location:** file path and line number
- **Issue:** what is wrong and why it matters
- **Suggestion:** specific fix or approach to resolve it

Summarize with: total issue count by severity and an overall recommendation (approve, request changes, or comment only).
