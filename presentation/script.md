# Presentation script

## Welcome and context

Hi everyone — I’m Tom Jagus, member of AI and Analytics Team. For the past years I have been working at the intersection of data, analytics, automation, tooling, reporting, process improvements, and spicing it up with AI. Today I want to share a project I’ve been developing that brings those topics together.

It’s called **LLMCogKit** — a toolkit that helps to define how LLMs should talk, structure responses, remember context, and even switch roles — all through a reusable configuration file.

We’ll walk through the problems it’s solving, how it works, and what it enables — and then I’ll show it in action. After the demo, I’ll share what’s coming next and leave time for questions.

## LLM Usage Today — The Problem

So here’s the situation most of us have run into:

You ask an LLM a question, and the answer is... okay. But the tone is off. Or it's too long. Or not structured the way you need. So you tweak the prompt. Then do it again next time. And again after that.

If you switch platforms — say from ChatGPT to Copilot or Claude — it’s like starting from scratch.

For individuals, that’s frustrating. For teams, it’s unscalable. And for anyone doing regular work, it's just repetitive.

Unless you’re a prompt engineering expert, it’s hard to make the assistant behave consistently across topics, tools, or tone.

So the question becomes:  
**How do we get the value of LLMs — without the unpredictability, repetition, or guesswork?**

That’s exactly what LLMCogKit is built to solve.

## Introducing LLMCogKit

LLMCogKit is a modular toolkit that lets you define — once — how you want LLMs to behave.

Through a guided setup, it captures your tone, formatting preferences, tools, workflows, values, and even custom assistant roles — and writes them into a single file.

That file works across platforms. Just load it into any AI chat bot session, say "Please read the attached profile and act accordingly," and the assistant will instantly adapt.

There’s no need to restate instructions, prompt for structure, or remind it how you like things — it just works, in your style, every time.

And because it’s built using Markdown and YAML, it’s human-readable, versionable, and shareable.

## How It Works — Profile Builder

The first module in LLMCogKit is the **Profile Builder** — a guided intake that builds your profile through natural conversation.

It covers five key areas:

- **Identity & Background** — your role, career journey, and where you create value
- **Workflows & Tools** — your stack, routines, and bottlenecks
- **Communication Preferences** — how you like to be spoken to and how chat bot responses should be formatted
- **Values & Patterns** — how you make decisions and approach problems
- **Personas** — optional assistant roles that match different working modes

Each section is conversational — the assistant asks follow-ups if needed, previews the result, and gives you a chance to revise before finalizing anything.

When you're done, you get a `profile.md` file — your assistant’s instruction manual.

## Live Demo 1 - Profile Builder

### Prompts

Please read the attached file and act accordingly.

Call me Tom.

I’d describe my role as a solution architect focused on end-to-end data workflows. I work with teams to improve how they collect, clean, analyze, and present data — mostly through automation and platform integration. I wear a few hats: sometimes I’m deep in Power BI and DAX, other times I’m building internal tools, defining KPIs, or mentoring team members. What ties it together is making things clearer, faster, and more maintainable — especially when dealing with messy or fragmented processes.

I started out in front-end web development — HTML, CSS, JavaScript — then moved into IT support roles. That gave me a solid grounding in systems thinking and user needs. Over time, I leaned into data: reporting, analytics, and eventually business intelligence. I’ve worked in service management, talent deployment, IT operations, and project delivery environments — mostly in large enterprises. I’ve always gravitated toward roles that mix tech and process design. What shaped my approach the most was working on cross-functional teams where I had to translate messy requirements into simple, scalable solutions.

I prefer a casual tone but professional voice. I want the assistant to sound natural, but not flippant or overly friendly. Think: clear, confident, and helpful. For formatting, I rely heavily on structure. Use bullet points for overviews, tables when comparing options or showing data, and code blocks or inline snippets where applicable. I also appreciate markdown-style headers when breaking down long responses. Clean, scannable, and well-structured replies help me move fast — especially when skimming for key details.

## Live Demo 2 - Profile Usage

### Use case 1 - Profile Activation + Structured Output

Please read the attached profile.md file and act accordingly.

Can you list 5 tools that could help automate weekly Power BI report distribution across teams?

### Use case 2 - Clarification Loop + Strategic Guidance

I want to improve how our reporting is received by leadership. Any thoughts?

Most of the reports are Power BI dashboards shared weekly. The feedback isn’t negative, but it’s often vague — like “too much info” or “not clear enough.” Some leaders prefer summary views, others like having access to detail, so it’s hard to satisfy everyone. I’d like to keep the design flexible but improve how the insights are delivered or emphasized.

### Use case 3 - Mid-Session Persona Switch + Code Cleanup

I’m working on a legacy Power BI report with multiple queries hitting different sources. It’s hard to maintain and slow to refresh. Any ideas for where to start simplifying it?

Here’s one of the messier queries. It’s been growing for a while. Also, switch to the “Power BI Expert” persona to handle the rewrite.

```
let
    Source = Excel.Workbook(File.Contents("C:\Users\user\Downloads\SalesReport.xlsx"), null, true),
    Sheet1_Sheet = Source{[Item="Sheet1",Kind="Sheet"]}[Data],
    ChangedType = Table.TransformColumnTypes(Sheet1_Sheet,{{"Column1", type text}, {"Column2", type any}}),
    RenamedColumns = Table.RenameColumns(ChangedType,{{"Column1", "Date"}, {"Column2", "Sales"}}),
    DuplicatedColumn = Table.DuplicateColumn(RenamedColumns, "Sales", "Sales - Copy"),
    FilteredRows = Table.SelectRows(DuplicatedColumn, each [Sales] <> null),
    SortedRows = Table.Sort(FilteredRows,{{"Date", Order.Ascending}}),
    RemovedColumns = Table.RemoveColumns(SortedRows,{"Sales - Copy"})
in
    RemovedColumns
```

## Project Status & Roadmap

Right now, the Profile Builder module is complete and working.

Next up are the **Templates for common tasks** (summarize, improve, rewrite, document, ideate etc.)

After that, we’re exploring:

- Onboarding Companion
- Automatic memory update suggestions based on conversation
- Profile adapters for ChatGPT, Copilot, Claude, Notion
- Team profiles and shared persona libraries

The goal is to make LLMs not just powerful — but predictable, contextual, and aligned with how you work.

## Wrap-Up & Q&A

LLMCogKit gives you a way to define assistant behavior once — and reuse it everywhere.

You get structure, tone, formatting, and context baked into every interaction — without the need to repeat yourself or re-engineer prompts.

It’s modular, portable, and designed to support real-world tasks across tools, roles, and teams.

That’s the vision — and the foundation is already working.

I’d love to hear your thoughts, feedback, or ideas on how this could support your work or team setups. Happy to take questions.
