# Contributing to Antigravity Axioms

Thank you for your interest in refining the core principles of our AI agents!

## The Philosophy
We treat our Axioms like production code. They must be:
1.  **Tested** (via `AXIOM_TESTS.md`).
2.  **Rationalized** (via `AXIOM_RATIONALE.md`).
3.  **Versioned** (via Semantic Versioning).

## Process for Changes

### 1. Propose
Open an issue using the **Axiom Proposal** template. You must answer:
-   **Why** is this change needed? (Tacit knowledge externalization)
-   **What** is the risk of *not* doing it?
-   **How** do we test it? (Concrete Pass/Fail example)

### 2. Review
We follow the `/review-axioms` workflow. Changes are evaluated against existing principles to ensure coherence. We avoid "Axiom Bloat"—if a new rule can be explained by an existing axiom, we prefer refining the existing one.

### 3. Release
Once merged, we use `standard-version` to tag a new release. This updates the global "Constitution" for all agents.

## Code of Conduct
Please read our [Code of Conduct](CODE_OF_CONDUCT.md). In short: Be excellent to each other. Focus on **Joy** and **Utility**.
