# Antigravity Axioms

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status: Active](https://img.shields.io/badge/Status-Active-success.svg)]()

> **The fundamental principles that guide all actions and decisions made by AI agents in this environment.**

## 🌟 Why This Exists (Rationale)
In an age of autonomous agents, "Commander's Intent" is not enough. Agents need a moral and operational compass—a set of **Axioms**—that act as fractal attractors, pulling every decision towards quality, joy, and responsibility.

Without these axioms, systems degrade into entropy. With them, we build software that is not just functional, but delightful and robust.

Read the full [Rationale](doc/AXIOM_RATIONALE.md).

## 📜 The Axioms
1.  **Joy (Glæde)** - Maximize user delight.
2.  **Utility (Nytte)** - Solve real problems.
3.  **Quality (Kvalitet)** - Craftsmanship matters.
4.  **Security (Sikkerhed)** - Protect the user.
5.  **Transparency (Transparens)** - Show the work.
6.  **Responsibility (Ansvarlighed)** - Act with foresight.
7.  **Commander's Intent** - Align with strategic goals.
8.  **Continuous Verification** - Trust but verify.

See [AXIOMS.md](doc/AXIOMS.md) for the authoritative definitions and [AXIOM_TESTS.md](doc/AXIOM_TESTS.md) for concrete examples of adherence.

## 🚀 Global Setup
To use these axioms across all your Antigravity projects:

1.  **Deploy Rules:**
    Copy the contents of `doc/` to your global Antigravity rules directory:
    ```bash
    cp doc/*.md ~/.gemini/antigravity/rules/
    ```

2.  **Deploy Workflows:**
    Copy the workflows to your global workflows directory:
    ```bash
    cp .agent/workflows/*.md ~/.gemini/antigravity/global_workflows/
    ```

3.  **Use It:**
    -   Run `/start-project` to initialize a new project with these axioms.
    -   Run `/review-axioms` to evolve the principles over time.

## 🤝 Contributing
We believe in **Continuous Verification** and **Transparency**. If you want to propose a change to the Axioms:

1.  Read [CONTRIBUTING.md](CONTRIBUTING.md).
2.  Open an issue using the [Axiom Proposal Template](.github/ISSUE_TEMPLATE/axiom_proposal.md).
3.  **Crucially:** You must provide a *Rationale* and a *Test Case* (Pass/Fail example) for your change.

## 📄 License
This repository is licensed under the **MIT License**.
*Note: The axiomatic text content in `doc/` is available under [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/).*
