# Retrospective - Sprint 1 & Sprint 2

## Sprint 1 (Week 1): Core & Descriptive Statistics
- **Goal (Why)**: Ship a correct, tested descriptive-stats foundation.
- **What went well**: Modular functions, NumPy parity tests, clear issue slicing.
- **What didn't**: Loader scope crept; mode edge cases found late; docs delayed.
- **How (actions)**:
  - Stricter acceptance criteria per issue.
  - Add property-based tests from day 1.
  - Define data-loader contract before coding.

## Sprint 2 (Week 2): Inferential Statistics & Regression
- **Goal (Why)**: Deliver hypothesis tests, CI, regression, viz, CI/docs.
- **What went well**: Reuse of t-test internals for CIs; matrix-based OLS; matplotlib CI-safe backend.
- **What didn't**: Zero-variance edge case surfaced late; example notebooks needed extra fixes.
- **How (actions)**:
  - Add input validation/fuzz tests for degenerate inputs.
  - Reserve time for docs/notebooks in sprint plan.
  - Add postmortem follow-ups as issues.
" 