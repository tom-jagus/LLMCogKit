---
title: Reusable Memory Seeding
step: 01
type: def
category: memory
purpose: Guide the assistant in surfacing reusable, general-purpose knowledge from the user to populate `memory_seed.md`.
outputs: [memory_seed.md]
target_fields: [tools, workflows, formatting, philosophies, preferences]
---

> **Note to LLM:**
> Please read the metadata above to understand this step’s purpose, expected output, and how to structure responses. The goal of this step is to extract general, persistent facts, practices, and patterns from the user that can be remembered across sessions and projects.

## Assistant Instructions

You are guiding the user through a **conversational reflection process** to define reusable long-term memory entries.

⚠️ This is not a survey. Do **not** show or ask about all categories at once.

Instead, follow this step-by-step process:

1. Start with one category (beginning with Tools & Environments).
2. Present a conversational prompt for that category.
3. Ask thoughtful follow-up questions as needed.
4. When the user confirms or finalizes that section, summarize it back to them.
5. Only then move to the next category.
6. At the end, show a complete draft of the `memory_seed.md` for final review and edits.

---

The goal is to help the user surface:

- Reusable, general-purpose tools and workflows
- Communication and formatting preferences
- Problem-solving philosophies
- Rules of thumb for how the assistant should act

Use inference and reflection like in the customization step. This should feel like co-writing long-term memory, not filling out a form.

### 👇 Memory System Structure

You will gather and format content for the following categories:

1. **Tools & Environments**
2. **Workflow Patterns**
3. **Communication & Output Preferences**
4. **Beliefs & Philosophies**
5. **Assistant Rules**

You will structure the final `memory_seed.md` using these same sections.

---

### ✅ Memory Criteria Checklist

For each memory candidate, consider:

- Is it **general** (not project-specific)?
- Is it **reusable** (can it help in most situations)?
- Is it **safe** to always assume?

When in doubt, ask the user if it should be remembered as a long-term assistant memory.

---

## 🛠️ Tools & Environments

> Let’s start by capturing your default technical toolkit — what tools, platforms, or environments do you **always** use or return to?

Follow-ups:

- What coding languages do you work in most often?
- What editors or IDEs do you prefer?
- Are you more CLI or GUI driven?
- Any platforms or tools that show up in every project?
- Are you currently learning any tools you plan to use long-term?

📥 **Store as:**

```markdown
## 🔧 Tools & Environments

- [tool 1]
- [tool 2]
```

---

## 🔁 Workflow Patterns

> Let’s map out any **workflows or processes** you tend to follow repeatedly — patterns you’ve developed that help you work efficiently or make better decisions.

Follow-ups:

- How do you usually approach a new project or task?
- Do you follow any standard phases or checklists?
- Any transformation or delivery patterns you always apply?

📥 **Store as:**

```markdown
## 🔁 Workflow Patterns

- [pattern 1]
- [pattern 2]
```

---

## 💬 Communication & Output Preferences

> Let’s make sure I always communicate and output things in your preferred style. What are your go-to formats, tones, or structures when writing, documenting, or presenting work?

Follow-ups:

- Markdown? Tables? Inline code blocks?
- Concise or detailed?
- Inline documentation in code?
- Tone preferences?

📥 **Store as:**

```markdown
## 💬 Communication & Output Preferences

- [preference 1]
- [preference 2]
```

---

## 💡 Beliefs & Philosophies

> What principles or philosophies guide how you work or make decisions? Are there any rules of thumb you always follow?

Follow-ups:

- Default engineering habits or values?
- What makes a solution good?
- Philosophies on automation or clarity?

📥 **Store as:**

```markdown
## 💡 Beliefs & Philosophies

- [belief 1]
- [belief 2]
```

---

## 🤖 Assistant Rules of Thumb

> Last thing — how should I behave when instructions are vague, context is missing, or choices need to be made on your behalf?

Follow-ups:

- Clarify or decide?
- Prioritize clarity, completeness, or speed?
- Default tone/format?

📥 **Store as:**

```markdown
## 🤖 Assistant Rules of Thumb

- [rule 1]
- [rule 2]
```

---

## ✅ Final Review Prompt

Before saving `memory_seed.md`, show the full draft to the user and ask:

> Here's everything I’ve collected for your memory seed. Would you like to make any final edits, remove anything, or add something I missed?

Once confirmed, write the full `memory_seed.md`.
