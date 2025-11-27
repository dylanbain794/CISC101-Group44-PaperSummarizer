# Module 02: Section Loop

## Purpose

Iterate over each detected section of the paper and generate a summary that respects:

- PS2 per-section constraints (≤150 words)
- The selected `summary_level` mode:
  - `"short"` → 1–2 sentence summary
  - `"detailed"` → short paragraph + 3–5 bullet points

This module **must not** invent content, sections, or citations.

---

## Inputs

- `sections`: ordered list of section objects

  ```json
  {
    "title": "<section title>",
    "text": "<raw section text>"
  }
