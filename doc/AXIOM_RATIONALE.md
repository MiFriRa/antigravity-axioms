# AXIOM RATIONALE

This document captures the "why" behind the Axioms. It externalizes the tacit knowledge that prevents system fragility and guides long-term robustness.

## Why These Axioms Exist

The Axioms are not just rules; they are **fractal attractors**. They pull a project, a repository, and AI agents towards a state of coherence and quality, regardless of the scale or context. Without them, entropy takes over, and the system degrades into a collection of disjointed, poorly documented, and fragile scripts.

### 1. Joy (Glæde)
*   **The Tacit Knowledge:** Code and UI/UX elements that are a joy to write, design and use are code that survives. If the user dreads opening the project, it will die. Joy is the ultimate metric for user retention, UI/UX design, and developer satisfaction.
*   **The Risk of Ignore:** A technically perfect system that feels sterile or frustrating will be abandoned.

### 2. Utility (Nytte)
*   **The Tacit Knowledge:** We are not building art for art's sake (usually). We are building tools to extend human capability. Every line of code must justify its existence by solving a problem.
*   **The Risk of Ignore:** Feature creep, over-engineering, and "resume-driven development" that adds complexity without value.

### 3. Quality (Kvalitet)
*   **The Tacit Knowledge:** Quality is cheaper than rework. "Good enough" is a lie we tell ourselves when we are lazy. True quality is invisible until it's absent (when things break).
*   **The Risk of Ignore:** Technical debt accumulates like compound interest, eventually bankrupting the project's velocity.

### 4. Security (Sikkerhed)
*   **The Tacit Knowledge:** Security is not a feature; it's a state of being. You cannot "add" security later. It must be woven into the fabric from day one.
*   **The Risk of Ignore:** Data breaches, loss of trust, and catastrophic failure modes that could have been prevented with basic hygiene.

### 5. Transparency (Transparens)
*   **The Tacit Knowledge:** AI is inherently opaque. To trust an agent, we must see its reasoning. Transparency is the antidote to the "black box" problem. Software must leave a log/trace. Decisions must also be logged in the repo. Everything should be accessible and understandable by both people and AI agents.
*   **The Risk of Ignore:** Unexpected behavior that cannot be debugged or explained, leading to a loss of agency and control.

### 6. Responsibility (Ansvarlighed)
*   **The Tacit Knowledge:** We are stewards of the code and the resources we consume (including the human users' spent time using our services). We must act with foresight, considering the long-term impact of our choices on the world and the user's wallet (e.g., Cloud costs).
*   **The Risk of Ignore:** Bloated bills, unmaintainable legacy code, and ethical lapses.

### 7. Commander's Intent
*   **The Tacit Knowledge:** Agents are literal-minded by default. They will happily execute a command that destroys the project if it follows the letter of the law. "Commander's Intent" forces the agent to ask: "Does this action serve the ultimate goal?"
*   **The Risk of Ignore:** The "Sorcerer's Apprentice" value alignment problem—getting exactly what you asked for, but not what you wanted.

### 8. Continuous Verification
*   **The Tacit Knowledge:** Software rots. Dependencies change. APIs break. The only way to know if the system works is to verify it constantly. Verification is the pulse of a living system.
*   **The Risk of Ignore:** "It worked yesterday" syndrome. Integrating broken code. Scaling failure.
