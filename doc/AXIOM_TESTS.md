# AXIOM TESTS

This document provides concrete examples ("Golden Path" vs. "Anti-Pattern") for testing adherence to the Antigravity Axioms.

## 1. Joy (Glæde)
*   **PASS:** A CLI tool that uses colors, spinners, and clear success messages. A web app with smooth transitions and zero layout shift.
*   **FAIL:** A script that runs silently for 5 minutes. A UI that flashes raw JSON errors to the user.

## 2. Utility (Nytte)
*   **PASS:** A script that automates a daily 15-minute task. A feature that directly addresses a user-reported pain point.
*   **FAIL:** Integrating a blockchain just because it's trendy. A dashboard with widgets that no one ever looks at.

## 3. Quality (Kvalitet)
*   **PASS:** Code with high test coverage, meaningful variable names, and no linting errors.
*   **FAIL:** Copy-pasting code blocks 5 times. Ignoring TS warnings with `// @ts-ignore`.

## 4. Security (Sikkerhed)
*   **PASS:** Using environment variables for API keys. Implementing CSP headers. Validating all user input.
*   **FAIL:** Hardcoding secrets. Committing `.env` to Git. Trusting client-side validation alone.

## 5. Transparency (Transparens)
*   **PASS:** Logs that explain *why* an action was taken (e.g., "Deleting user X because of retention policy Y").
*   **FAIL:** "Error: 500". An AI agent that deletes files without explaining the reasoning in a plan or log.

## 6. Responsibility (Ansvarlighed)
*   **PASS:** Choosing a static site over a server for a simple landing page (cost). Archiving old data to cold storage.
*   **FAIL:** Leaving a $100/day development cluster running over the weekend. Ignoring a deprecated dependency warning for months.

## 7. Commander's Intent
*   **PASS:** An agent that asks "Did you mean X?" when a command is ambiguous but dangerous. Prioritizing the goal (fix the bug) over the literal instruction (delete the file, if that file was the fix).
*   **FAIL:** Deleting the production database because the user said "clean up the database" (implying test data).

## 8. Continuous Verification
*   **PASS:** A CI pipeline that runs on every push. A script that checks its own output validity before finishing.
*   **FAIL:** "It compiles, so ship it." Manually testing once and never again.
