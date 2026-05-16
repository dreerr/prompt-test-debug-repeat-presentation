---
layout: section
---

# Day 1: Tuesday
## Basics & Tools

---

# Admin

<v-clicks>

- Attendance required — sign in via Discord
- Max 1 absence
- Week goal: feel the loop

</v-clicks>

---
layout: center
---

<SlidevVideo v-click autoplay controls>
  <source :src="'/The Man in the Bottle Trim.mp4'" type="video/mp4">
</SlidevVideo>

Source: [The Man in the Bottle (Twilight Zone, 1960)](https://en.wikipedia.org/wiki/The_Man_in_the_Bottle)

---
layout: center
---

# Intro Round

Three questions. No pressure.

<v-clicks>

- What do you want to **build** this week?
- What are you **not** interested in?
- Which LLM tools have you used? What have you already vibe-coded?

</v-clicks>

---
layout: center
---

<SlidevVideo v-click autoplay controls>
  <source :src="'/Exact Instructions Challenge Trim.mp4'" type="video/mp4">
</SlidevVideo>

Source: [Josh Darnit: Exact Instructions Challenge (2017)](https://www.youtube.com/watch?v=cDA3_5982h8)


---
layout: section
---

# Exercise: Prompt Without a Computer

---
layout: center
---

# Pen & Paper

Partner up. No screens.

**Describe an animation to your neighbor**
as if you were typing it into an AI at the board.

<v-click>

> Goal: feel what *precise and complete* means
> before you open a laptop.

</v-click>

<!--
Give them ~8 min. Then actually prompt one or two descriptions live.
The point: vague language fails. Precision isn't pedantry, it's communication.
-->

---
layout: section
---

# Part I: Understanding AI

---

# Prompting for Coding Agents

<v-clicks>

- **Context before task** — what's the project, what exists, what's the goal. Then the ask.
- **Name your frameworks** — "use Tailwind", "vanilla JS" — specificity kills ambiguity
- **Show, don't just tell** — screenshot or URL beats a paragraph
- **One main task, 2–3 constraints** — not too vague, not 10 requirements at once
- **Describe the result, not the path** — "clicking the button changes the color"
- **Explicit negatives** — "no external libs", "don't touch the CSS", "no new files"

</v-clicks>

---
layout: center
---

# What are LLMs actually good at?

*Let's check before we assume.*

---
layout: two-cols
---

# LLMs: Strengths

<v-clicks>

- Boilerplate & standard patterns
- Explaining and commenting code
- Generating variants
- Debugging *with* an error message
- Rephrasing & translating

</v-clicks>

::right::

# LLMs: Struggles

<v-clicks>

- Logic across many steps
- Counting, math, exact quotes
- Spotting their own mistakes
- Tracking large codebases
- Anything after training cutoff

</v-clicks>

<!--
Let them name some before revealing. Ask the room first.
-->

---
layout: center
---

# The Context Window

> The AI's short-term memory for one session.

<v-clicks>

**What's inside:**
System prompt · conversation history · open files · error messages · tool results

**Why it matters:**
Full or noisy → quality drops. New session = clean slate.

**Rule of thumb:**
Short sessions. Targeted context. Don't cram everything in.

</v-clicks>

---

# Three More Things

<v-clicks>

**Hallucinations**
The model invents facts confidently. Test everything. Never trust blindly.

**Model differences**
Not all LLMs are equal — context size, capabilities, and costs vary.

**Tokens & costs**
Tokens are the unit of work. Relevant for rate limits and API pricing.

</v-clicks>

---
layout: section
---

# Part II: Understanding Code

---
layout: center
---

# Quick quiz.

I'll show you a term.
You tell me what it is.

---
layout: center
---

# Markup

*e.g. HTML*

<v-click>

Describes structure and content.
Not a program. No logic. Just: **"what is what."**

</v-click>

---
layout: center
---

# Scripting Language

*e.g. JavaScript, Python*

<v-click>

Instructions that execute at runtime.
Runs as-is — no build step needed.

</v-click>

---
layout: center
---

# Frontend vs. Backend

<v-click>

**Frontend** — runs in the browser. Visible.
**Backend** — runs on a server. Invisible. Handles logic, data, auth.

</v-click>

---
layout: center
---

# API

<v-click>

A defined interface between two systems.

*"How do I talk to X?"*

</v-click>

---
layout: center
---

# Library vs. Package

<v-click>

**Library** — ready-made code for a specific job.
**Package** — how that code gets distributed and installed.

`npm install x` → done.

</v-click>

---

# Paradigms to Recognize

*(Not to memorize — just enough to follow along)*

<v-clicks>

- **Version Control** — Git. No more `_final_FINAL_wirklichFinal.html`.
- **Package Management** — `npm install x` → x is available
- **APIs** — weather app asks a server via HTTP, gets JSON back
- **Type Safety** — `"5" + 5` in JS is `"55"`. Types matter.
- **Compiled vs. Interpreted** — Python runs directly; C needs a build step
- **Rendering Environments** — same JS, three contexts: browser, Node, terminal
- **Data Formats** — JSON travels between systems; CSV is a text spreadsheet
- **Environments** — `.env`, `package.json`, `requirements.txt` = "here's what you need"

</v-clicks>

---

# VS Code — Quick Map

<v-clicks>

- **Explorer** (left) — file & folder tree
- **Editor** (center) — where you type
- **Terminal** (bottom) — your main work surface
- **Source Control** (Git icon) — stage, commit, push
- **Extensions** — add capabilities
- **Command Palette** (`Cmd/Ctrl+Shift+P`) — everything by keyboard

</v-clicks>

<v-click>

*First task: Install GitHub Copilot and connect your GitHub account.*

</v-click>

---

# Shell Basics

```bash
cd foldername    # go into a folder
cd ..            # go up one level
ls               # list contents (Mac/Linux)
node file.js     # run a Node script
python file.py   # run a Python script
```

<v-click>

**Shortcuts:**
- `Tab` — autocomplete paths and commands
- `↑ / ↓` — navigate command history

*Exercise: navigate from home to your project folder. Run a script.*

</v-click>

---

# Version Control

<v-clicks>

**Key terms:**
- `repository` — project + full history
- `commit` — a named snapshot
- `branch` — a parallel timeline
- `push / pull` — sync with remote
- `merge` — combine branches
- `conflict` — two edits clash (solvable)

</v-clicks>

<v-click>

In VS Code: Source Control panel → stage → commit message → push.

</v-click>

---
layout: section
---

# Exercise: GitHub Copilot

---

# The Loop — For Real This Time

**In pairs:**

<v-clicks>

1. Chat vs. Inline Completion vs. Edits — when to use what?
2. Agent Mode — what it can and can't do
3. Usage tokens — what costs what?
4. **Build a simple HTML page together via Copilot**

</v-clicks>

<v-click>

> Feel the loop:
> **Prompt → Output → Test → Correct → Repeat**

</v-click>

<!--
Circulate. Watch how prompts are written. Only step in after >10 min of being stuck.
-->
