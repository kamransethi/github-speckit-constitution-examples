# GitHub Spec Kit — Sample Constitutions

Example constitution files for [GitHub Spec Kit](https://githubnext.com/projects/spec-kit), demonstrating how to write constitutions that actually shape AI-assisted development across different stacks and risk profiles.

These samples accompany the [Writing Constitutions That Work](doc/spec-kit-constitution-playbook.md) playbook. Each one is a complete, production-style constitution written for a fictional — but realistic — banking repository.

---

## What's in this repo

| File | System | Stack | What it demonstrates |
|---|---|---|---|
| [constitution-cobol-batch-processing.md](constitution-cobol-batch-processing.md) | **EOD-Settle** — end-of-day settlement & reconciliation batch suite | COBOL · z/OS · JCL | Batch window enforcement, checkpoint/restart, control totals as source of truth, copybook change control, idempotent reruns, and runbook-gated deployment |
| [constitution-iso20022-microservice.md](constitution-iso20022-microservice.md) | **PayBridge** — ISO 20022 message translation microservice | Java · Spring Boot | Schema validation that rejects (never repairs), idempotent transformations with lineage, bounded MT legacy isolation, CBPR+ compliance verification, structured address enforcement, and sanctions screening controls |
| [constitution-ux-application.md](constitution-ux-application.md) | **AccountHub** — customer-facing digital banking web application | React · TypeScript | Accessibility as a merge gate, no sensitive data in the browser, design-system-first styling, performance budgets enforced in CI, explicit API failure handling, and contract-driven backend integration |

---

## What is a Spec Kit constitution?

A constitution is the operating contract that every Spec Kit command (`/speckit.plan`, `/speckit.tasks`, `/speckit.implement`) reads before it touches your code. It's not documentation for humans — it's the set of rules and architectural facts that make an AI coding assistant reason from ground truth instead of guessing.

A good constitution is:

- **Falsifiable** — every principle either changes a future plan or fails a review, or it gets cut
- **Grounded in real paths** — rules point at actual files and directories, not abstract concepts
- **Layered** — org-wide non-negotiables (security, compliance, audit) sit in a shared "Section 0," while repo-specific architecture and conventions live in the repo layer

---

## How to use these samples

These are **reference examples**, not templates to copy verbatim. Use them to:

1. **See the pattern** — each constitution follows a consistent structure: repo overview → core principles (with rationale) → constraints table → workflow & quality gates → governance
2. **Calibrate depth to risk** — the COBOL batch suite and ISO 20022 microservice are Tier 1 (Critical / Complex) examples; the UX application shows the same rigor applied to a frontend
3. **Understand what "falsifiable" looks like** — every principle names real files, real packages, and real consequences for violation

For the full methodology — including the two-layer model, tiering framework, conditional-loading patterns, and common pitfalls — see the [playbook](doc/spec-kit-constitution-playbook.md).

---

## Quick links

- 📖 [Writing Constitutions That Work — Playbook](doc/spec-kit-constitution-playbook.md)
- 🏦 [COBOL Batch Processing Constitution](constitution-cobol-batch-processing.md) — EOD-Settle
- 💱 [ISO 20022 Microservice Constitution](constitution-iso20022-microservice.md) — PayBridge
- 🖥️ [UX Application Constitution](constitution-ux-application.md) — AccountHub
