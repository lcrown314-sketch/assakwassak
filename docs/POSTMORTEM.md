# Postmortem - NaN p-values in t-test (Virtual Incident)

## Summary
- **Incident**: t-test returned NaN p-values for zero-variance (constant) samples.
- **Severity**: Medium (incorrect inferential results, but no data loss).
- **Detected**: During Sprint 2 example notebook walkthrough.

## Why
- **Root cause**: Division by zero in standard-deviation path; no precondition validation.
- **Contributing**: Unit tests lacked constant/degenerate inputs; example notebooks untested in CI initially.

## What
- **Impact**: Users received NaN statistics/p-values and invalid CIs for constant groups.
- **Scope**: Affected ttest_1samp, ttest_ind, and dependent confint_mean paths.
- **What we did**: Hotfix added explicit zero-variance handling + tests; notebook added to CI smoke checks.

## How
- **Fix**: Raise ValueError (or documented NaN with guard) on zero variance; add input validation at function boundaries.
- **Detection improvement**: Property-based/fuzz tests including constants and tiny n.
- **Prevention**: Input validation checklist in PR template; degenerate-case test fixtures; notebook smoke job in CI.
- **Follow-up issues**: validation hardening, fuzz tests, docs update for edge cases.
" 