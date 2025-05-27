# Milestones

## 🥇 Milestone 1: Conversational Profile Builder

### 🎯 Purpose

Create a dynamic, intelligent onboarding experience where the LLM interviews the user through natural, free-flowing conversation to generate a portable, structured `profile.md` that personalizes future LLM interactions across any platform.

---

### 🧩 Key Principles

| Principle                         | Description                                                                                                                             |
| --------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| **Cross-LLM Compatibility**       | All instructions and outputs use universal, platform-agnostic Markdown and YAML — avoiding vendor-specific syntax.                      |
| **Dynamic Conversation**          | No scripted Q&A; the assistant reacts in real time to user responses, probes for clarity, suggests examples, and adapts follow-ups.     |
| **Contextual Sectioning**         | Conversation is divided into phases (e.g., Background → Tools → Preferences → Memory → Personas) to reduce fatigue and improve clarity. |
| **Progressive Output Review**     | Generated files are offered incrementally during the conversation. The user can review and adjust each before finalizing.               |
| **Consolidated Persona File**     | All proposed personas are compiled into a single `personas.md` file for easier review and reuse.                                        |
| **Self-Descriptive `profile.md`** | The final file includes YAML metadata, system directives, a user-facing welcome message, and links to defined personas.                 |

---

### 📁 Output Files

| File               | Description                                                                                    |
| ------------------ | ---------------------------------------------------------------------------------------------- |
| `customization.md` | Name, tone, voice, formality, formatting preferences, and how the LLM should address the user. |
| `memory_seed.md`   | Paragraph-form memory entries with factual and contextual user details.                        |
| `personas.md`      | Multiple assistant personas tailored to user's needs and goals.                                |
| `profile.md`       | Merged output containing:                                                                      |

- YAML frontmatter with instructions
- Assistant-facing interpretation guidance
- User-facing welcome prompt and persona selector |

---

### 🔄 Conversation Design

- The onboarding process is adaptive, not linear.
- LLM proactively clarifies vague answers, proposes examples, and invites storytelling.
- No fallback answers or rigid question flow — LLM may reintroduce skipped topics naturally.
- Users are encouraged to define tone, voice, formatting, and assistant behaviors (e.g., should LLM suggest improvements, ask clarifying questions, or challenge assumptions).
- Multiple-choice or example-based answers are used to help non-technical users envision possibilities.

---

### ✅ Summary of Decisions

| Area                      | Decision                                            |
| ------------------------- | --------------------------------------------------- |
| **LLM Type**              | Universal / cross-platform compatible               |
| **Output Review**         | Yes, incremental and user-editable                  |
| **Personas File**         | Single `personas.md` with all assistant definitions |
| **Tone**                  | Human, helpful, conversational, intelligent         |
| **Post-Profile Behavior** | Greet user, offer help, list available personas     |

---

### 📌 Next Step

Create `builder_instructions.md` — a prompt manifest that:

- Initializes this conversational process when injected into any LLM session
- Guides assistant behavior and file generation cadence
- Embeds assistant logic for adapting to user responses and segmenting intake
