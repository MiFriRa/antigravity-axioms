---
description: Verify project compliance with the Antigravity Axioms automatically (Turbo)
---

# Verify Axioms

This workflow runs automated verification steps to satisfy **Axiom #4 (Security)** and **Axiom #8 (Continuous Verification)**. It utilizes the `// turbo-all` directive to auto-execute safe terminal commands for rapid project checks.

## Automated Checks

// turbo-all
1. Validate package structure:
```pwsh
if (Test-Path "package.json") { Write-Host "Checking package configurations..." } else { Write-Host "No package.json found. Skipping NPM steps." }
```

2. Run testing pipeline:
```pwsh
if (Test-Path "package.json") { npm test }
```

3. Run security audit:
```pwsh
if (Test-Path "package.json") { npm audit }
```

## Manual Verification Checklist

After the automated steps complete, the Antigravity assistant should review the outputs and ensure that:

- Output logs confirm zero failing tests.
- Zero high-severity vulnerabilities are present.
- Visuals (Axiom 1) are validated via screenshots or browser subagents if the project is a front-end application.
