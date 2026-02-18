---
description: Review and update Antigravity Axioms.
---
# Review Axioms Workflow

This workflow ensures the Axioms evolve with the user's needs and experience.

1.  **Read Current Axioms**
    -   Read [AXIOMS.md](file:///c:/Users/mikke/Projects/antigravity-axioms/doc/AXIOMS.md)
    -   Read [AXIOM_RATIONALE.md](file:///c:/Users/mikke/Projects/antigravity-axioms/doc/AXIOM_RATIONALE.md)

2.  **Reflect**
    -   [ ] Have we encountered any situations where the axioms were insufficient or conflicting?
    -   [ ] Is there new "tacit knowledge" that needs to be externalized in the Rationale?

3.  **Update**
    -   Edit `AXIOMS.md` or `AXIOM_RATIONALE.md` as needed.
    -   Ensure changes are clear and additive (avoid breaking existing alignment if possible).

4.  **Release**
    -   Run `npm run release` in `c:\Users\mikke\Projects\antigravity-axioms` to version the changes and generate a changelog.
    -   Push changes to remote (if applicable).
