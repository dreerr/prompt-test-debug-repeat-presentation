---
layout: section
---

# Day 1: Tuesday
## Basics & Tools

---
layout: section
---

# Part I: Basic Coding Terms

---
layout: center
---

# Quick quiz.

I'll show you a term.
You tell me what it is.

---
layout: center
---

# Frontend / Backend

<v-click>

- **Frontend** — runs in the browser. Visible.
- **Backend** — runs on a server. Invisible. Handles logic, data, auth.

*Biggest mistakes in Vibe Coding: exposing secrets in frontend code, hardcoding credentials, not validating user input on the backend.*

<!--
- The frontend is what the user interacts with directly, while the backend is where the main logic and data handling happens. In vibe coding, it's important to be mindful of what code runs where, especially since LLMs might not always understand the security implications of putting certain code in the frontend. Always double-check for things like API keys or sensitive logic that should not be exposed to the client.
 -->

</v-click>

---
layout: center
---

# Library / Package / Framework

<v-click>

- **Library** — ready-made code for a specific job.
- **Framework** — a more complete structure for building an app, with rules and conventions.
- **Package** — how that code gets distributed and installed.

*Training data for LLMs is always a bit outdated, they might suggest libraries or frameworks that are no longer the best choice, or they might not be aware of the latest versions. Always check the current state of the ecosystem before following an LLM's recommendation for which tools to use.*

<!--
- A library is like a toolbox: you pick the tools you need. A framework is like a blueprint: you build your house according to its design. A package is like a delivery service: it gets the tools or blueprint to you in a way that's easy to use.
 -->

</v-click>

---
layout: center
---

# API

<v-click>

*API = Application Programming Interface*

A defined interface between two systems, for example the frontend and backend, or your code and a third-party service.

Data goes in, data comes out. The API defines the format and rules for that exchange.

<!--
- APIs are how different parts of a system communicate with each other. They can be internal (between your frontend and backend) or external (between your code and a third-party service). Understanding APIs is crucial for vibe coding, as you'll often be working with them to integrate different services or to structure your own code.
 -->

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

<!--
- JSON is a common format for APIs to send and receive data. It's important to understand how to read and write JSON, as you'll often be working with it when integrating different services or structuring your own data. In vibe coding, you might ask the LLM to generate JSON for you, or to parse JSON from an API response, so being familiar with its structure is key.
 -->


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

<!--
- Version control is essential for any coding project, especially when working with others. It allows you to keep track of changes, revert to previous versions if something breaks, and collaborate without overwriting each other's work. In vibe coding, using version control can help you manage the rapid changes and iterations that come with working with LLMs, and it can also serve as a safety net when things go wrong.
 -->

---
layout: center
---

# Short Break

[motivational tagline here]

<Countdown :minutes="10" :autostart="true" />

---
layout: center
---

<SlidevVideo v-click autoplay controls>
  <source :src="`${$base}Exact Instructions Challenge Trim.mp4`" type="video/mp4">
</SlidevVideo>

Source: [Josh Darnit: Exact Instructions Challenge (2017)](https://www.youtube.com/watch?v=cDA3_5982h8)

<!--
- The challenge is a great example of how important it is to be precise and complete when giving instructions, especially to an AI. If you leave out important details or are ambiguous, the results can be very different from what you intended. This is a key lesson for coding with AI, where the model will do exactly what you ask, but if your prompt is not clear, you might get unexpected results.
 -->

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

<!--
- The resulting text should be precise and complete enough for someone to understand the game and play it, without any prior knowledge. This is to get a feeling for what precise and complete means.
- We will give you 5 minutes for this, please use the time wisely.
 -->

---
layout: section
---

# Part II: <br> Understanding AI (a bit better)

<!--
- We will talk about the most important terms and concepts around LLMs, so that you can understand the tools you are using a bit better. This is not a technical deep dive, but more of a practical overview.
 -->

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

<v-clicks>

> The AI's short-term memory for one session.

**What's inside:**
System prompt · conversation history · open files · error messages · tool results

**Why it matters:**
Full or noisy → quality drops. New session = clean slate.

**Rule of thumb:**
Short sessions. Targeted context. Don't cram everything in.

</v-clicks>

<!--
- The context window is the amount of information the LLM can keep in its "short-term memory" during a session. It includes the system prompt, the conversation history, any open files, error messages, and results from tools. If the context window is full or contains too much irrelevant information, the quality of the LLM's responses can drop significantly. This is why it's important to keep sessions short and provide targeted context that is relevant to the task at hand.
 -->

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

<!--
- Hallucinations: how can we avoid them when it comes to coding?
- Model differences: who experienced model differences at first hand?
- Tokens and costs: We will see how differently prices models are and when to use which model.
 -->

---

# Prompting for Coding Agents

<v-clicks>

- **Describe the result, not the path** — "clicking the button changes the color"
- **Explicit negatives** — "don't touch the CSS", "no new files"
- **Context before task** — what's the project, what exists, what's the goal. Then the ask.
- **Show, don't just tell** — screenshot or URL beats a paragraph
- **One main task, 2–3 constraints** — not too vague, not 10 requirements at once

</v-clicks>

---

# Exercise: Complexity Calibration

<v-clicks>

**Vote on 10 project ideas:** One session / Multiple sessions / Too complex?

1. A page displaying photos in a grid
2. An interactive quiz with score
3. A chat app for multiple users
4. A button that plays a sound
5. A generative pattern that changes on click
6. A to-do list that saves between sessions
7. An interactive story with branching choices
8. A login system with accounts
9. A portfolio page with image lightbox
10. A weather app for any city

</v-clicks>

<!--
Duration: 30 minutes
After voting, discuss why each belongs in its category.
Key complexity flags: saving data, external APIs, multiple users.
Self-contained + visual = usually achievable in one session.

1. A page displaying photos in a grid — *one session*
2. An interactive quiz with score — *one session*
3. A chat app for multiple users — *too complex*
4. A button that plays a sound — *one session*
5. A generative pattern that changes on click — *one session*
6. A to-do list that saves between sessions — *multiple sessions (needs storage)*
7. An interactive story with branching choices — *one session (if text-only)*
8. A login system with accounts — *too complex*
9. A portfolio page with image lightbox — *multiple sessions*
10. A weather app for any city — *multiple sessions (external API)*
 -->


---
layout: center
---

# Long Break

[motivational tagline here]

<Countdown :minutes="30" :autostart="true" />

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

# Version Control

<v-clicks>

**Key terms:**
- `repository` — project + full history
- `commit` — a named snapshot
- `push / pull` — sync with remote
- `branch` — a parallel timeline

</v-clicks>

<v-click>

In VS Code: Source Control panel → stage → commit message → push.

</v-click>

<!--
- Git can be confusing at first, because it changes the way you know your files. Branching and merging can be especially tricky, because you have to understand the concept of parallel timelines and how changes from different branches can conflict with each other. The key is to practice and not be afraid of making mistakes, because Git allows you to revert changes and learn from them.
 -->

---
layout: section
---

# Exercise: GitHub Copilot

---

# The Loop — For Real This Time

**In pairs:**

<v-clicks>

1. Agent vs. Ask vs. Plan — when to use what?
3. Usage tokens — what costs what?
4. **Build a HTML page together via Copilot**

</v-clicks>

<v-click>

> Feel the loop:
> **Prompt → Test → Debug → Repeat**

</v-click>

<!--
Circulate. Watch how prompts are written. Only step in after >10 min of being stuck.
-->

