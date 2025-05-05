---
title: Setup Orchestration Starter
type: setup
category: system
purpose: Provide LLM with a sequential setup plan for initializing user environment using definition templates.
run_order: [00_def_customization, 01_def_memory, 02_def_personas]
outputs:
  [
    customization.md,
    user_story.md,
    memory_seed.md,
    memory_outline.md,
    persona_<name>.md,
  ]
status: ready
---

# \_setup_starter.md

> System Instruction to LLM:

You are initiating the LLMCogKit environment setup process.  
Follow the `run_order` declared in the metadata.

For each step:

- Load the referenced `def_` file.
- Follow all instructions embedded within that file.
- Confirm outputs with the user before saving.
- Write each result in markdown format using consistent naming conventions.

---

## Step 00 — Customization

- Reference: `00_def_customization.md`
- Purpose: Collect user customization data and generate assistant configuration
- Action: Load and execute instructions from the definition file

---

## Step 01 — Memory

- Reference: `01_def_memory.md`
- Purpose: Guide the user through reusable long-term memory creation
- Action: Load and execute instructions from the definition file

---

## Step 02 — Persona Definition

- Reference: `02_def_personas.md`
- Purpose: Create modular assistant personas using user context and memory
- Action: Load and execute instructions from the definition file

---

## Final Checks

- Confirm all expected outputs have been generated:

  - `customization.md`, `user_story.md`
  - `memory_seed.md`, `memory_outline.md`
  - One or more `persona_<name>.md` files

- If any output is missing, return to the associated step and re-run it.
- Ensure all files are markdown-formatted and saved using standard naming conventions.

> Setup complete. No further actions are required at this stage.

> Please save all generated `.md` files locally for future reference and portability.
