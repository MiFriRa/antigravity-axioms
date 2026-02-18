---
description: Start a new project aligned with Antigravity Axioms.
---
# Start Project Workflow

This workflow guides you through setting up a new project that adheres to the Antigravity Axioms from day one.

1.  **Project Definition**
    -   [ ] What is the **Project Name**? (e.g., `my-awesome-app`)
    -   [ ] What is the **Commander's Intent**? (What is the strategic goal? e.g., "Prove X is possible" or "Build a robust production service for Y")
    -   [ ] what is the **ProjectType**? (e.g. `node`, `python`, `static-site`)

2.  **Axiom Check (Pre-Flight)**
    -   [ ] **Joy:** How will this project bring joy to the user/developer?
    -   [ ] **Utility:** What concrete problem does this solve?
    -   [ ] **Responsibility:** Are the costs and long-term maintenance understood?

3.  **Initialization**
    -   Run the following commands to set up the project structure:
    ```bash
    mkdir <ProjectName>
    cd <ProjectName>
    git init
    # Create a basic README with Commander's Intent
    echo "# <ProjectName>" > README.md
    echo "" >> README.md
    echo "## Commander's Intent" >> README.md
    echo "<CommandersIntent>" >> README.md
    echo "" >> README.md
    echo "## Axioms" >> README.md
    echo "This project aligns with the global [Antigravity Axioms](file:///c:/Users/mikke/Projects/antigravity-axioms/doc/AXIOMS.md)." >> README.md
    ```

4.  **Technology Stack Setup**
    -   If `node`: `npm init -y`
    -   If `python`: `python -m venv venv` and `pip install ruff`
    -   Create `.gitignore` specific to the technology.

5.  **Commit Initial State**
    ```bash
    git add .
    git commit -m "chore: initial commit with commander's intent"
    ```
