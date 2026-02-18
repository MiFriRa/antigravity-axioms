---
description: Review and update Antigravity Axioms with rigorous validation.
---
# Review Axioms Workflow

This workflow ensures the Axioms evolve with the user's needs and experience, backed by concrete examples and rationale.

1.  **Context Loading & Reflection**
    -   [ ] Read [AXIOMS.md](file:///c:/Users/mikke/Projects/antigravity-axioms/doc/AXIOMS.md)
    -   [ ] Read [AXIOM_RATIONALE.md](file:///c:/Users/mikke/Projects/antigravity-axioms/doc/AXIOM_RATIONALE.md)
    -   [ ] Read [AXIOM_TESTS.md](file:///c:/Users/mikke/Projects/antigravity-axioms/doc/AXIOM_TESTS.md) for current examples.
    -   [ ] **Question:** Have we encountered any situations where the axioms were insufficient or conflicting? Is there new "tacit knowledge"?

2.  **Define the Change**
    -   [ ] What is the new Principle or Refinement?
    -   [ ] **Constraint:** Does this conflict with existing axioms? (Check generic vs. specific)

3.  **Update Artifacts (Simultaneous)**
    -   [ ] **Update `AXIOMS.md`**: Add or modify the text.
    -   [ ] **Update `AXIOM_RATIONALE.md`**: Explain the *why*. What risk does this mitigate? What tacit knowledge is captured?
    -   [ ] **Update `AXIOM_TESTS.md`**: Add a concrete "PASS" and "FAIL" example. **No axiom change without a test case.**

4.  **Impact Analysis**
    -   [ ] **Check:** Will this break existing projects?
    -   [ ] **Check:** Does this apply to non-software projects (e.g., articles)?
    -   [ ] If major change, consider version bump strategy (Major vs. Minor).

5.  **Release**
    -   Run `npm run release` in `c:\Users\mikke\Projects\antigravity-axioms` to version the changes and generate a changelog.
    -   Push changes to remote.
