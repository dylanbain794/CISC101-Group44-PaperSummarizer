# Research Paper Summarizer

This repository contains a modular, extensible system prompt architecture designed for an LLM-based **Research Paper Summarizer**. The system processes full academic papers and produces structured outputs including section summaries, expert and lay summaries, glossary terms, and quality checks.

The project is built using a **multi-module internal architecture**, inspired by the Travel Planner system pattern, with clear responsibilities and guardrails to enforce accuracy and prevent hallucination.

---

## 🚀 Repository Components

### `system_prompt.md`
The core system prompt that instructs an LLM how to behave when summarizing a research paper. It includes:

- Greeting & tone rules
- Required user inputs
- Boundaries (no hallucination, no invented citations)
- Output requirements
- Workflow stages
- Formatting rules
- Embedded PS2 Summarization Specification block

This file defines the **overall behavior and expectations** of the summarizer.

---

### `/modules/` Folder
Contains the internal processing modules that the system executes in sequence.

Each module handles a specific part of the summarization workflow:

1. `intake_setup.md`
   - Validates inputs
   - Normalizes section headings
   - Detects missing or short sections

2. `section_loop.md`
   - Iterates through each section
   - Generates ≤150-word summaries
   - Flags short or incomplete content

3. `guardrails.md`
   - Prevents hallucination
   - Enforces citation rules
   - Handles long papers using PS2 chunking strategy

4. `rendering_refinement.md`
   - Assembles final outputs
   - Produces:
     - section table
     - combined summary (≤300 words)
     - expert & lay summaries
     - mini-glossary
     - warnings report

5. `citation_extractor.md`
   - Extracts citations explicitly present in the text
   - No fabrication allowed

6. `key_contributions.md`
   - Identifies 3–5 major contributions
   - Must be grounded in the source text

---

## 🧩 Architecture Overview

The system follows this workflow:

1. Intake
2. Validate Inputs
3. Normalize Sections
4. Section Loop
5. Guardrails
6. Additional Student Modules
7. Refinement
8. Output Assembly
9. Final Checks

This ensures consistent formatting, accuracy, and compliance with the PS2 specification.

---

## 📄 PS2 Specification Integration

This summarizer explicitly incorporates the Week 10 PS2 Summarization Specification, including:

- Inputs
- Outputs
- Word limits
- Anti-redundancy rules
- Context window strategies

The full specification block is included at the bottom of `system_prompt.md`.

---

## 📊 Purpose of the Repository

This repository serves as:

- A meta-prompt engineering project
- A modular summarization system design
- A reusable LLM architecture template
- A deliverable for coursework demonstrating:
  - specification integration
  - modularity
  - guardrails
  - output formatting

---

## ✅ README Analysis (PLACE CONTENT HERE)

Write your README analysis or reflection below this heading.

This section is where you will:

- explain why the repo is structured this way
- justify design decisions
- connect to PS2 requirements
- reflect on modularity and guardrails
- evaluate effectiveness

Example starter:

> This repository demonstrates how modular prompt engineering improves reliability and structure in LLM summarization tasks...

---

## 📌 How to Use This Repo

You can run this system by:

- Copying `system_prompt.md` into an LLM as a system instruction
- Providing a full academic paper as input
- Allowing the modules to execute sequentially

---
