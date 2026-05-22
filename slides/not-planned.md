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
layout: center
---

# Markup Language

<v-click>

*e.g. HTML (HyperText Markup Language)*

> The word *markup* is derived from the traditional publishing practice of *marking up* a manuscript

Describes structure and content.\
Not a program. No logic. Just: **"what is what."**

**Other common markup languages:**
- Markdown — lightweight formatting for text
- YAML — config files and data serialization
- XML — data storage and transfer
</v-click>

<!--
- Markup languages are not programming languages because they don't have logic or control flow. They are just a way to describe the structure and content of a document or data. They are often used in conjunction with programming languages, but they serve a different purpose.
- That is ont the other hand not true, in HTML you can have JavaScript embedded, and in XML you can have XSLT which is a programming language. But the point is that the markup itself is not a programming language, it's just a way to describe data.
 -->

---
layout: center
---

# Scripting Language

<v-click>

*e.g. JavaScript, Python*

Instructions that execute at runtime.\
Runs as-is — no build step needed.

*Why "scripting"?* Historically, they were for automating tasks (scripts) rather than building full applications. Now the line is blurry.

</v-click>

<!--
- What is a build step? It's a process that transforms source code into a form that can be executed. For compiled languages, this is the compilation step.
 -->


---
layout: center
---

# Programming Language

<v-click>

*e.g. Java, C++*

Requires a build step (compilation) to run.\
Often faster and more powerful, but less flexible for quick changes.

*Why "programming"?* They were designed for building complex software (programs) rather than automating tasks. Again, the line is blurry.

</v-click>

<!--
For vibe coding, scripting languages are often more convenient because they allow for faster iteration without the overhead of a build step. However, programming languages can be used in a vibe coding style as well, especially with modern tools that have fast compilation or hot reloading. Errors in programming languages can be more disruptive because they might prevent the code from running at all, whereas scripting languages might allow you to run parts of the code and fix errors on the fly. This is something to keep in mind when choosing your tools for vibe coding.
 -->

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

<!--
- Most important is the meaning of charaters like spaces, dots, and slashes. For example, `cd ..` means "go up one level" because `..` refers to the parent directory. The `ls` command lists the contents of the current directory, and `node file.js` or `python file.py` runs a script with the respective runtime. The shortcuts can save you a lot of time, especially when navigating through directories or recalling previous commands.
 -->

---

# What is Vibe Coding?

<v-click>

There's a new kind of coding I call "vibe coding", where you fully give in to the vibes, embrace exponentials, and forget that the code even exists. It's possible because the LLMs (e.g. Cursor Composer w Sonnet) are getting too good. Also I just talk to Composer with SuperWhisper so I barely even touch the keyboard. I ask for the dumbest things like "decrease the padding on the sidebar by half" because I'm too lazy to find it. I "Accept All" always, I don't read the diffs anymore. When I get error messages I just copy paste them in with no comment, usually that fixes it. The code grows beyond my usual comprehension, I'd have to really read through it for a while. Sometimes the LLMs can't fix a bug so I just work around it or ask for random changes until it goes away. It's not too bad for throwaway weekend projects, but still quite amusing. I'm building a project or webapp, but it's not really coding - I just see stuff, say stuff, run stuff, and copy paste stuff, and it mostly works.

*Andrej Karpathy / @karpathy / 3. Feb. 2025*

</v-click>

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

# More Copilot Practice

<v-clicks>

**When to use what:**
- Chat — exploration, questions, explaining
- Inline completion — in-flow suggestions
- Agent Mode — bigger tasks with context

**Common traps:**
- Context too long → quality drops
- Prompts too vague → unpredictable output
- No spec → no way to know if it's done

</v-clicks>
