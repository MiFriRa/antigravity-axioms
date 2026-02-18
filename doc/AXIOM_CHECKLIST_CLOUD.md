# AXIOM CHECKLIST: Google Cloud & Firebase

Use this checklist to ensure your cloud projects align with the Antigravity Axioms.

## 🚀 Commander's Intent & Utility
- [ ] **Define the Goal:** Is this a prototype (speed) or production (scale)? Document it in `README.md`.
- [ ] **Solve a Real Problem:** Does this service need to exist? Can it be a simple Cloud Function or static site instead?
- [ ] **Cost Awareness (Responsibility):** Have you checked pricing for the selected services (e.g., Cloud Run vs. App Engine)?
- [ ] **Set Cost Alerts:** Configure a budget alert in Google Cloud Billing (e.g., stopping at $10/month for hobby projects).

## 🛡️ Security & Responsibility
- [ ] **API Keys:**
    - [ ] Restrict keys to specific APIs (e.g., only Firestore, not Maps).
    - [ ] Add application restrictions (HTTP referrers for web, Android/iOS app constraints).
- [ ] **Firestore / Storage Rules:**
    - [ ] **NEVER** use `allow read, write: if true;` in production.
    - [ ] Write granular rules based on auth state (`request.auth != null`).
    - [ ] Test rules with the Firebase Emulator.
- [ ] **IAM Roles:**
    - [ ] Use Service Accounts with least privilege (don't use `Editor` or `Owner` for runtime services).
    - [ ] Rotate keys regularly if used outside GCP.
- [ ] **Secrets Management:**
    - [ ] Use Google Secret Manager for sensitive env vars (API keys, DB passwords).
    - [ ] Never commit `.env` files with real secrets to Git.

## ⚡ Quality & Continuous Verification
- [ ] **CI/CD Pipeline:**
    - [ ] Set up GitHub Actions or Cloud Build to deploy automatically on push to `main`.
    - [ ] Include a build/test step in the pipeline.
- [ ] **Linting & Formatting:**
    - [ ] Enforce code style (e.g., Ruff for Python, Prettier for JS) in CI.
- [ ] **Automated Tests:**
    - [ ] Write unit tests for core logic.
    - [ ] Write integration tests for API endpoints (using emulators).

## 👁️ Transparency & Joy
- [ ] **Structured Logging:**
    - [ ] Use structured logging (JSON) so logs are queryable in Cloud Logging.
    - [ ] Include `trace_id` to correlate logs across services.
- [ ] **Error Handling:**
    - [ ] Return meaningful HTTP error codes (4xx vs 5xx).
    - [ ] Provide user-friendly error messages in the frontend, not raw stack traces.
- [ ] **Documentation:**
    - [ ] Keep `README.md` updated with "How to deploy" and "How to run locally".
    - [ ] Document architecture decisions (ADRs) if non-obvious.

## 🔄 Verification Step
- [ ] **Manual Vibe Check:** Does the deployment feel "snappy" and joyful to use?
- [ ] **Verify Axioms:** Run this checklist before every major release.
