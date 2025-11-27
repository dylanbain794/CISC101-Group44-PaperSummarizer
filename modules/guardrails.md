# Module 03: Guardrails

## Purpose

Ensure that all summaries:

- Only include information explicitly found in the provided text
- Do NOT invent:
  - claims
  - results
  - equations
  - citations
  - sections
- Provide clear warnings when content cannot be summarized reliably

This module enforces the **“only use what’s in the paper”** rule.

---

## Inputs

- Section summary objects from Module 02
- Raw section text
- `evidence_mode` flag (optional)

---

## Evidence Mode (New Requirement B)

You MUST implement a strict evidence behavior using:

```text
evidence_mode = "strict"
