---
layout: section
---

# Day 1: Tuesday
## Basics & Tools

---
layout: center
---

<SlidevVideo v-click autoplay controls>
  <source :src="`${$base}Exact Instructions Challenge Trim.mp4`" type="video/mp4">
</SlidevVideo>

Source: [Josh Darnit: Exact Instructions Challenge (2017)](https://www.youtube.com/watch?v=cDA3_5982h8)


---
layout: section
---

# Exercise: <br> Prompt Without a Computer

---
layout: center
---

# Pen & Paper

No screens.

Describe the game of **Tic Tac Toe**
without using the words <br/>
"Tic Tac Toe", "three", "row", or "line".

> Goal: feel what *precise and complete* means

<Countdown :minutes="5" :autostart="false" />


---
layout: section
---

# Part I: <br> Understanding AI (a bit better)

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

<SlidevVideo v-click autoplay controls>
  <source :src="`${$base}The Man in the Bottle Trim.mp4`" type="video/mp4">
</SlidevVideo>

Source: [The Man in the Bottle (Twilight Zone, 1960)](https://en.wikipedia.org/wiki/The_Man_in_the_Bottle)

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

## Hallucinations
The model invents facts confidently. Test everything. Never trust blindly.

## Model differences
Not all LLMs are equal — context size, capabilities, and costs vary.

## Tokens & costs
Tokens are the unit of work. Relevant for rate limits and API pricing.

</v-clicks>

---

# What is Vibe Coding?

<v-click>

> There's a new kind of coding I call "vibe coding", where you fully give in to the vibes, embrace exponentials, and forget that the code even exists. It's possible because the LLMs (e.g. Cursor Composer w Sonnet) are getting too good. Also I just talk to Composer with SuperWhisper so I barely even touch the keyboard. I ask for the dumbest things like "decrease the padding on the sidebar by half" because I'm too lazy to find it. I "Accept All" always, I don't read the diffs anymore. When I get error messages I just copy paste them in with no comment, usually that fixes it. The code grows beyond my usual comprehension, I'd have to really read through it for a while. Sometimes the LLMs can't fix a bug so I just work around it or ask for random changes until it goes away. It's not too bad for throwaway weekend projects, but still quite amusing. I'm building a project or webapp, but it's not really coding - I just see stuff, say stuff, run stuff, and copy paste stuff, and it mostly works.

*Andrej Karpathy / @karpathy / 3. Feb. 2025*

</v-click>

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

# Markup Language


<v-clicks>

*e.g. HTML (HyperText Markup Language)*

> The word *markup* is derived from the traditional publishing practice of *marking up* a manuscript

Describes structure and content.\
Not a program. No logic. Just: **"what is what."**

**Other common markup languages:**
- XML — data storage and transfer
- Markdown — lightweight formatting for text
- YAML — config files and data serialization
</v-clicks>

---
layout: center
---

# Scripting Language

<v-clicks>

*e.g. JavaScript, Python*

Instructions that execute at runtime.
Runs as-is — no build step needed.

*Why "scripting"?* Historically, they were for automating tasks (scripts) rather than building full applications. Now the line is blurry.

</v-clicks>

---
layout: center
---

# Programming Language

<v-clicks>

*e.g. Java, C++*

Requires a build step (compilation) to run.\
Often faster and more powerful, but less flexible for quick changes.

*Why "programming"?* They were designed for building complex software (programs) rather than automating tasks. Again, the line is blurry.

</v-clicks>

---
layout: center
---

# Frontend / Backend

<v-click>

- **Frontend** — runs in the browser. Visible.
- **Backend** — runs on a server. Invisible. Handles logic, data, auth.

*Biggest mistakes in Vibe Coding: exposing secrets in frontend code, hardcoding credentials, not validating user input on the backend.*

</v-click>

---
layout: center
---

# Library / Package / Framework

<v-click>

- **Library** — ready-made code for a specific job.
- **Framework** — a more complete structure for building an app, with rules and conventions.
- **Package** — how that code gets distributed and installed.

`npm install x` → done.\
`pip install x` → done.

</v-click>

---
layout: center
---

# API

<v-click>

*API = Application Programming Interface*

A defined interface between two systems, for example the frontend and backend, or your code and a third-party service.

Data goes in, data comes out. The API defines the format and rules for that exchange.

Today most APIs are HTTP-based, where you send a request to a URL and get JSON back. But the concept is broader than that.

</v-click>

---
layout: two-cols
---

# JSON

<v-click>

*JSON = JavaScript Object Notation*

A lightweight data format that's easy for humans to read and write, and easy for machines to parse.

</v-click>

::right::

<v-click>

```json
{
  "first_name": "John",
  "last_name": "Smith",
  "is_alive": true,
  "age": 27,
  "address": {
    "street_address": "21 2nd Street",
    "city": "New York",
    "state": "NY",
    "postal_code": "10021-3100"
  },
  "phone_numbers": [
    {
      "type": "home",
      "number": "212 555-1234"
    },
    {
      "type": "office",
      "number": "646 555-4567"
    }
  ],
  "children": [
    "Catherine",
    "Thomas",
    "Trevor"
  ]
}
```

</v-click>

---
layout: two-cols
---

# Version Control

<v-click>

A system for tracking changes to code over time. It allows multiple people to collaborate, keeps a history of edits, and helps manage different versions of a project.

**Git** is the most popular version control system today. It uses a distributed model, where each developer has a full copy of the repository, and changes are shared via commits and pushes.

**GitHub** is a platform built on top of Git that provides hosting for repositories, collaboration tools, and a web interface for managing code.

*No more `_final_FINAL_wirklichFinal.html`*
</v-click>

::right::

<v-click>


<img :src="`${$base}git.svg`" />

</v-click>

---
layout: center
---

# Short Break

[motivational tagline here]

<Countdown :minutes="10" :autostart="true" />

---
layout: section
---

# Hands-On: VS Code & Git

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
