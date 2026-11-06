# TIL - Python Statistics Project (14 Days)

## Day 1 - Project Skeleton & Packaging (Issue #1)
- Why: Establish a reproducible, installable package before adding math.
- What: Adopted src/statkit layout, pyproject.toml, pytest/ruff config, tests dir.
- How: pip install -e . + import statkit; CI-ready from day one.

## Day 2 - Mean / Median / Mode (Issue #2)
- Why: Central tendency is the foundation of descriptive stats.
- What: Implemented mean/median and multimodal mode; empty input raises ValueError.
- How: Validated against NumPy; added edge-case tests.

## Day 3 - Variance / Std / Covariance (Issue #3)
- Why: Quantify spread and co-movement.
- What: Added ddof support (0/1) for all three functions.
- How: Cross-checked results with NumPy to floating tolerance.

## Day 4 - Quantiles / Percentiles / IQR (Issue #4)
- Why: Robust spread measures needed beyond std.
- What: Implemented linear interpolation quantiles and IQR.
- How: Tested against numpy.percentile across random datasets.

## Day 5 - Dataset Summary (Issue #5)
- Why: Single-call descriptive report for EDA.
- What: summary(data) returns count, mean, std, min, quartiles, max.
- How: Reused Day 2-4 primitives to avoid duplicated math.

## Day 6 - Data Loading (CSV/JSON) (Issue #6)
- Why: Stats functions are useless without ingestion.
- What: load_csv/load_json returning dicts/arrays; encoding + missing-value reporting.
- How: Added malformed-file tests and encoding fixtures.

## Day 7 - Descriptive Test Suite (Issue #7)
- Why: Lock correctness before expanding scope.
- What: Pytest suite + property-based checks vs NumPy.
- How: Parametrized fixtures; discovered mode edge cases early.

## Day 8 - t-tests (Issue #8)
- Why: Core inferential capability.
- What: One/two-sample t-tests with statistic, p-value, CI.
- How: Validated vs scipy.stats; noted zero-variance edge case.

## Day 9 - Chi-Square Tests (Issue #9)
- Why: Categorical association testing.
- What: Goodness-of-fit and independence tests with degrees of freedom.
- How: Checked contingency-table handling and expected-frequency rules.

## Day 10 - Confidence Intervals (Issue #10)
- Why: Estimation complements hypothesis tests.
- What: Mean (t/z) and proportion (z) CIs at configurable confidence.
- How: Reused t-test internals; boundary tests for proportions.

## Day 11 - OLS Regression (Issue #11)
- Why: Baseline predictive model.
- What: Simple/multiple OLS: coefficients, residuals, R-squared, p-values.
- How: Matrix algebra with NumPy; singular-matrix awareness.

## Day 12 - Correlation (Issue #12)
- Why: Measure linear/monotonic association.
- What: Pearson and Spearman with coefficients and p-values.
- How: Compared against SciPy; handled ties in ranks.

## Day 13 - Plotting Utilities (Issue #13)
- Why: Visual EDA and result communication.
- What: Histogram, boxplot, scatter with regression line; save-to-file.
- How: Matplotlib non-interactive backend for CI/test safety.

## Day 14 - CI + Examples & Docs (Issues #14, #15)
- Why: Automate quality and onboard users.
- What: GitHub Actions (pytest + ruff + coverage) and example notebooks/README quickstart.
- How: Triggered on push/PR; kept notebooks reproducible.
