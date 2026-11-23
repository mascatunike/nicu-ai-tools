---
name: ecc-engineering
description: Apply disciplined engineering practices for implementation, testing, debugging, review, and secure delivery.
---

# ECC Engineering — Curated Local Subset

This local plugin contains a compact subset of engineering practices inspired by Everything Claude Code (ECC). It is not the complete upstream ECC package.

## Before implementation
- Inspect the repository instructions, architecture, tests, and existing conventions.
- Clarify expected behavior and acceptance criteria.
- Write a short implementation plan for non-trivial changes.
- Prefer the smallest coherent change.

## Test-driven development
1. Write or identify a test that demonstrates the expected behavior.
2. Run it and confirm it fails for the intended reason.
3. Implement the minimum change.
4. Run the focused test, then relevant regression tests.
5. Refactor only while tests remain green.

## Debugging
- Reproduce the issue before changing code.
- Capture the exact error, inputs, environment, and relevant logs.
- Form one hypothesis at a time and test it.
- Trace the cause rather than suppressing symptoms.
- Add a regression test after fixing the defect.

## Code review
- Check correctness, edge cases, security, error handling, and compatibility.
- Cite exact files and lines for findings.
- Do not invent defects or approve code that was not inspected.
- Separate blockers from non-blocking suggestions.

## Secure delivery
- Never hardcode secrets or expose sensitive data in logs.
- Validate untrusted input and enforce authorization at the trust boundary.
- Avoid destructive commands and production changes without explicit approval.
- Report tests run, tests not run, and known limitations.

For the complete upstream project, see https://github.com/affaan-m/ECC. This folder intentionally contains only this curated local skill, not the full 328-skill upstream collection.