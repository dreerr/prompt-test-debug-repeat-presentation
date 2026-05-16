---
theme: default
title: "Prompt, Test, Debug, Repeat"
author: Julian Palacz
colorSchema: dark
fonts:
  sans: JetBrains Mono
  mono: JetBrains Mono
  provider: google
transition: fade
lineNumbers: false
aspectRatio: 16/9
canvasWidth: 980
defaults:
  layout: default
---

<style>
:root {
  --slidev-theme-primary: #e8ff00;
  --slidev-theme-background: #0c0c0c;
}

.slidev-layout {
  background: #0c0c0c;
  color: #e8e8e8;
  font-family: 'JetBrains Mono', monospace;
}

h1 {
  color: #e8ff00 !important;
  font-weight: 700;
  letter-spacing: -0.02em;
}

h2 {
  color: #e8ff00 !important;
  font-weight: 500;
}

h3 {
  color: #aaaaaa;
  font-weight: 400;
}

.accent { color: #e8ff00; }
.dim { color: #666; }
.warn { color: #ff6b35; }
.ok { color: #7fff7f; }

.tag {
  display: inline-block;
  background: #1a1a1a;
  border: 1px solid #333;
  padding: 2px 10px;
  font-size: 0.75em;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: #888;
}

.day-label {
  position: absolute;
  top: 2rem;
  right: 2rem;
  font-size: 0.7em;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: #444;
}

.quiz-prompt {
  background: #111;
  border-left: 3px solid #e8ff00;
  padding: 1.2em 1.6em;
  font-family: monospace;
  font-size: 0.95em;
  line-height: 1.6;
  color: #ccc;
  margin: 1em 0;
}

.quiz-answer {
  background: #0d1a0d;
  border-left: 3px solid #7fff7f;
  padding: 1em 1.4em;
  font-size: 0.85em;
  line-height: 1.6;
  color: #aaa;
  margin: 0.5em 0;
}

.quiz-trap {
  background: #1a0d0d;
  border-left: 3px solid #ff6b35;
  padding: 1em 1.4em;
  font-size: 0.85em;
  line-height: 1.5;
  color: #aaa;
  margin: 0.5em 0;
}

.big-number {
  font-size: 5em;
  font-weight: 700;
  color: #e8ff00;
  line-height: 1;
}

.paradigm-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 1em;
  margin-top: 1em;
}

.paradigm-item {
  background: #111;
  border: 1px solid #222;
  padding: 1em;
  font-size: 0.8em;
}

.paradigm-item .label {
  color: #e8ff00;
  font-weight: 600;
  margin-bottom: 0.4em;
  font-size: 0.85em;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}

.paradigm-item .desc {
  color: #777;
  font-size: 0.8em;
  line-height: 1.5;
}

.week-grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 0.6em;
  margin-top: 1.5em;
}

.week-day {
  background: #111;
  border: 1px solid #222;
  padding: 0.8em 0.6em;
  text-align: center;
  font-size: 0.75em;
}

.week-day.active {
  border-color: #e8ff00;
}

.week-day .day-name {
  color: #444;
  font-size: 0.75em;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  margin-bottom: 0.5em;
}

.week-day .day-content {
  color: #ccc;
  line-height: 1.4;
}

.week-day.active .day-content {
  color: #e8ff00;
}

.person-card {
  display: flex;
  gap: 1em;
  align-items: start;
  background: #111;
  border: 1px solid #222;
  padding: 1.2em;
  margin-bottom: 0.8em;
}

.person-card .name {
  color: #e8ff00;
  font-weight: 600;
  margin-bottom: 0.3em;
}

.person-card .role {
  color: #666;
  font-size: 0.8em;
  margin-bottom: 0.5em;
  letter-spacing: 0.05em;
  text-transform: uppercase;
}

.person-card .desc {
  color: #999;
  font-size: 0.85em;
  line-height: 1.5;
}

.manifesto {
  font-size: 1.05em;
  line-height: 1.8;
  color: #ccc;
}

.manifesto strong {
  color: #fff;
}
</style>

---
layout: cover
---

<div class="day-label">Tag 1</div>

# Prompt, Test,<br>Debug, Repeat.

<div style="margin-top: 1.5em; color: #555; font-size: 0.75em; letter-spacing: 0.15em; text-transform: uppercase;">
Vibe Coding Workshop &nbsp;·&nbsp; narrativemedia.design &nbsp;·&nbsp; Angewandte
</div>

<!--
Willkommen. Handy weg, Laptop zu. Erstmal ein Quiz.
-->

---

<div class="day-label">Tag 1 / Prompt Quiz</div>

# Prompt Quiz

<div style="color: #555; font-size: 0.85em; margin-bottom: 2em;">Was macht die KI mit diesem Prompt?</div>

<div class="quiz-prompt">
Write me a website.
</div>

<div v-click class="quiz-answer">
→ Produziert irgendetwas. Wahrscheinlich HTML mit inline CSS, vielleicht React,<br>
vielleicht plain JS. Fragt nicht nach. Trifft Annahmen über alles.
</div>

<div v-click style="margin-top: 1.5em; color: #555; font-size: 0.8em;">
💡 Die Maschine füllt Lücken — immer, confident, ohne Warnung.
</div>

<!--
Erstes Quiz: kurz, knapp. Studis sollen Antworten shouten oder auf Karten schreiben.
-->

---

<div class="day-label">Tag 1 / Prompt Quiz</div>

# Prompt Quiz

<div style="color: #555; font-size: 0.85em; margin-bottom: 2em;">Was ist das Problem mit diesem Prompt?</div>

<div class="quiz-prompt">
Fix the bug.
</div>

<div v-click class="quiz-trap">
⚠ Kein Kontext. Kein Code. Kein Stack. Kein Error-Message.<br>
Die KI wird trotzdem eine Antwort liefern. Und klingt dabei völlig sicher.
</div>

<div v-click style="margin-top: 1em;">
<div class="quiz-prompt">
Fix the bug. Here's the error: [paste error] — Here's the relevant code: [paste code] — I'm using Node 20, the issue happens when I call the API endpoint /users after login.
</div>
</div>

<div v-click style="color: #7fff7f; font-size: 0.85em; margin-top: 0.8em;">
→ Kontext ist alles. Kein Kontext = Raten auf hohem Niveau.
</div>

---

<div class="day-label">Tag 1 / Prompt Quiz</div>

# Prompt Quiz

<div style="color: #555; font-size: 0.85em; margin-bottom: 2em;">Was passiert hier?</div>

<div class="quiz-prompt">
I've been working on this for 3 hours. Please just make it work. I need it for tomorrow.
</div>

<div v-click class="quiz-trap">
⚠ Die KI fühlt deinen Stress — und halluziniert trotzdem.<br>
Emotionaler Kontext ≠ technischer Kontext.
</div>

<div v-click style="margin-top: 1em; color: #888; font-size: 0.85em;">
Die Maschine antwortet auf das, was du schreibst — nicht auf das, was du meinst.<br>
Sie kennt deinen Projekt-State nicht. Sie erinnert sich nicht an gestern.
</div>

<div v-click style="margin-top: 1.5em; color: #e8ff00; font-size: 0.9em; font-weight: 600;">
Bullshit erkennen. Kontext geben. Systematisch debuggen.
</div>

---

<div class="day-label">Tag 1 / Prompt Quiz</div>

# Prompt Quiz

<div style="color: #555; font-size: 0.85em; margin-bottom: 2em;">Welcher Prompt ist besser?</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1em;">
<div>

**A**
<div class="quiz-prompt">
Make a button that does something when clicked.
</div>

</div>
<div v-click>

**B**
<div class="quiz-prompt">
Add an onClick handler to the Button component in src/components/Button.tsx. When clicked, it should call the onSubmit prop and disable itself until the Promise resolves. TypeScript, no external libraries.
</div>

</div>
</div>

<div v-click style="margin-top: 1.5em; color: #7fff7f; font-size: 0.85em;">
→ Spezifität ist Kontrolle. Vague prompts = vague outputs = endloses Nachbessern.
</div>

<!--
Quiz-Abschluss: kurze Diskussion. Was haben die Studis bemerkt?
-->

---
layout: section
---

<div class="day-label">Tag 1</div>

# Was du hier<br>wirklich lernst.

---

<div class="day-label">Tag 1</div>

<div class="manifesto" style="max-width: 720px; margin: 0 auto; padding-top: 1em;">

<v-click>

Du lernst nicht coden.

</v-click>

<v-click>

Du lernst, **eine Maschine zu beauftragen**, die dir confident falschen Code liefert, deinen Projektkontext vergisst und Komplexität aufbläst, die niemand braucht.

</v-click>

<v-click>

Deine Arbeit: **Kontrolle behalten. Bullshit erkennen. Systematisch debuggen.**

</v-click>

</div>

<!--
Langsam lesen. Pausen lassen.
-->

---

<div class="day-label">Tag 1</div>

<div class="manifesto" style="max-width: 720px; margin: 0 auto; padding-top: 1em;">

Das ist die Realität — **keine Magie**, sondern ein neues Handwerk.

<v-click>

Technische Arbeit kommissionieren und managen, **ohne den Output selbst schreiben zu können**.

</v-click>

<v-click>

<div style="margin-top: 1.5em; padding: 1.2em; border-left: 3px solid #e8ff00; background: #0f0f0f;">
In meiner künstlerischen Praxis beschäftige ich mich viel mit Daten und deren Ästhetik — genau diese kritische Distanz zum Werkzeug brauchst du auch hier.
</div>

</v-click>

<v-click>

<div style="margin-top: 1.2em; color: #666; font-size: 0.85em;">
Keine Coding-Kenntnisse erforderlich.
</div>

</v-click>

</div>

---
layout: two-cols
---

<div class="day-label">Tag 1</div>

# Keine Vorkenntnisse<br>erforderlich.

<div style="margin-top: 1.5em;">

<v-clicks>

- ~~Syntax lernen~~
- ~~Algorithmen verstehen~~
- ~~Stack konfigurieren~~
- ~~Deployment manuell aufsetzen~~

</v-clicks>

<div v-click style="margin-top: 1.5em; color: #e8ff00;">

Das übernimmt die Maschine.

</div>

</div>

::right::

<div style="padding-left: 2em; padding-top: 3em;">

<v-clicks>

- Anforderungen präzise formulieren
- Output kritisch prüfen
- Kontext aufrechterhalten
- Fehler strukturiert eingrenzen
- Maschine führen, nicht folgen

</v-clicks>

<div v-click style="margin-top: 1.5em; color: #e8ff00;">

Das lernst du hier.

</div>

</div>

---
layout: section
---

<div class="day-label">Tag 1</div>

# Die Woche.

---

<div class="day-label">Tag 1</div>

# 5 Tage. 1 Hackathon.

<div class="week-grid">

<div class="week-day active">
<div class="day-name">Mo</div>
<div class="day-content">Prompt Quiz<br>Grundlagen<br>Paradigmen</div>
</div>

<div class="week-day active">
<div class="day-name">Di</div>
<div class="day-content">Peter:<br>Spec-driven Dev<br><br>Esad:<br>Agentic Coding</div>
</div>

<div class="week-day">
<div class="day-name">Mi</div>
<div class="day-content" style="color: #555;">Freies Arbeiten<br>mit Jonas</div>
</div>

<div class="week-day">
<div class="day-name">Do</div>
<div class="day-content" style="color: #555;">Freies Arbeiten<br>mit Jonas</div>
</div>

<div class="week-day">
<div class="day-name">Fr</div>
<div class="day-content" style="color: #ff6b35;">Hackathon<br>🔥</div>
</div>

</div>

<div v-click style="margin-top: 1.5em; color: #555; font-size: 0.8em;">
Support die ganze Woche: Jonas vom Coding Lab · Freitag: gemeinsamer Hackathon
</div>

---

<div class="day-label">Tag 1</div>

# Die Crew.

<div v-click class="person-card">
<div style="min-width: 60px; color: #e8ff00; font-size: 1.5em; font-weight: 700;">J</div>
<div>
<div class="name">Jonas</div>
<div class="role">Coding Lab · Support die ganze Woche</div>
<div class="desc">Technischer Begleiter der Woche. Fragen, Stuck-Momente, Setups — Jonas ist dabei.</div>
</div>
</div>

<div v-click class="person-card">
<div style="min-width: 60px; color: #e8ff00; font-size: 1.5em; font-weight: 700;">P</div>
<div>
<div class="name">Peter</div>
<div class="role">Senior Developer · Dienstag</div>
<div class="desc">Spec-Driven Development — wie man ein Projekt so präzise spezifiziert, dass eine Maschine es zuverlässig umsetzen kann.</div>
</div>
</div>

<div v-click class="person-card">
<div style="min-width: 60px; color: #e8ff00; font-size: 1.5em; font-weight: 700;">E</div>
<div>
<div class="name">Esad</div>
<div class="role">Senior Developer · Dienstag</div>
<div class="desc">Advanced Agentic Coding — einen Prozess dirigieren, nicht einen Prompt. Der große Bruder des Vibe Codings.</div>
</div>
</div>

---
layout: section
---

<div class="day-label">Tag 1</div>

# Werkzeuge &<br>Paradigmen.

<div style="margin-top: 1em; color: #555; font-size: 0.8em;">Keine Lernziele — Orientierung.</div>

---

<div class="day-label">Tag 1</div>

# Das Vokabular.

<div style="color: #666; font-size: 0.8em; margin-bottom: 1.5em;">Wenn das Modell sagt, du brauchst einen Backend-Server — du solltest wissen, was das bedeutet.</div>

<div class="paradigm-grid">

<div v-click class="paradigm-item">
<div class="label">Git</div>
<div class="desc">Versionskontrolle. Warum "ich hab's abgespeichert" nicht reicht.</div>
</div>

<div v-click class="paradigm-item">
<div class="label">Package Management</div>
<div class="desc">npm, pip, cargo — wie Abhängigkeiten verwaltet werden.</div>
</div>

<div v-click class="paradigm-item">
<div class="label">APIs</div>
<div class="desc">Wie Systeme miteinander reden. REST, JSON, HTTP.</div>
</div>

<div v-click class="paradigm-item">
<div class="label">Type Safety</div>
<div class="desc">Warum Maschinen Typen brauchen — und Menschen eigentlich auch sollten.</div>
</div>

<div v-click class="paradigm-item">
<div class="label">Rendering</div>
<div class="desc">Browser vs. Server vs. Terminal. Wo läuft dein Code?</div>
</div>

<div v-click class="paradigm-item">
<div class="label">Datenformate</div>
<div class="desc">JSON, CSV — was zwischen Systemen reist.</div>
</div>

</div>

<div v-click style="margin-top: 1.2em; color: #555; font-size: 0.75em; letter-spacing: 0.05em;">
+ Environments — warum "works on my machine" keine Entschuldigung ist.
</div>

---
layout: center
---

<div class="day-label">Tag 1</div>

<div style="text-align: center;">

<div class="big-number">?</div>

<div style="margin-top: 1em; color: #666; font-size: 0.9em;">Fragen zum ersten Tag?</div>

<div v-click style="margin-top: 2em; color: #e8ff00; font-size: 0.8em; letter-spacing: 0.1em; text-transform: uppercase;">
Morgen: Spec-driven Development & Agentic Coding
</div>

</div>

---
layout: cover
---

<div class="day-label">Tag 2</div>

# Tag 2.

<div style="margin-top: 1em; color: #555; font-size: 0.85em;">
Paradigmen · Peter · Esad
</div>

<!--
Kurze Recap vom Vortag. Was hat wer ausprobiert?
-->

---
layout: section
---

<div class="day-label">Tag 2</div>

# Technische<br>Orientierung.

<div style="margin-top: 0.8em; color: #555; font-size: 0.8em;">Das, was du kennen solltest — nicht unbedingt können.</div>

---

<div class="day-label">Tag 2</div>

# Git — Versionskontrolle

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1em;">

<div>

**Ohne Git:**

<div v-click class="quiz-trap" style="font-size: 0.82em; margin-top: 0.8em;">
projekt_final.zip<br>
projekt_final_v2.zip<br>
projekt_final_WIRKLICH_FINAL.zip<br>
projekt_final_USE_THIS_ONE.zip
</div>

</div>

<div v-click>

**Mit Git:**

<div class="quiz-answer" style="font-size: 0.82em; margin-top: 0.8em;">
<span style="color: #7fff7f;">commit a3f9c2e</span> "add user login"<br>
<span style="color: #7fff7f;">commit b12d8e1</span> "fix API timeout"<br>
<span style="color: #7fff7f;">commit c44f901</span> "initial setup"
</div>

</div>

</div>

<div v-click style="margin-top: 1.5em; color: #888; font-size: 0.85em; line-height: 1.6;">
Git tracked jede Änderung. Du kannst zu jedem Punkt zurück.<br>
Wenn das Modell deinen Code zerstört — git gibt ihn dir zurück.
</div>

<div v-click style="margin-top: 1em; color: #e8ff00; font-size: 0.85em;">
Das Modell arbeitet am besten mit Git. Kleine Commits. Oft committen.
</div>

---

<div class="day-label">Tag 2</div>

# APIs — Wie Systeme reden

<div style="margin-top: 1em; color: #888; font-size: 0.85em; margin-bottom: 1.5em; line-height: 1.6;">
Eine API ist ein Vertrag: "Schick mir das in diesem Format, ich schick dir das zurück."
</div>

<div v-click>

```
POST https://api.example.com/users
Content-Type: application/json

{
  "name": "Maria",
  "email": "maria@angewandte.ac.at"
}
```

</div>

<div v-click style="margin-top: 1.2em; color: #888; font-size: 0.85em; line-height: 1.6;">

→ Das reist als Text durch das Internet. JSON ist das meistgenutzte Format.

</div>

<div v-click style="margin-top: 1em; color: #e8ff00; font-size: 0.85em;">
Wenn du mit externen Services arbeitest (KI, Wetterdaten, Maps) — du redest über APIs.
</div>

---

<div class="day-label">Tag 2</div>

# Datenformate

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 2em; margin-top: 1.2em;">

<div>

**JSON**
<div v-click class="quiz-prompt" style="font-size: 0.8em; margin-top: 0.8em;">
{<br>
&nbsp;&nbsp;"name": "Maria",<br>
&nbsp;&nbsp;"year": 2024,<br>
&nbsp;&nbsp;"active": true<br>
}
</div>
<div v-click style="font-size: 0.75em; color: #666; margin-top: 0.6em;">Zwischen APIs, Config-Files, KI-Antworten</div>

</div>

<div>

**CSV**
<div v-click class="quiz-prompt" style="font-size: 0.8em; margin-top: 0.8em;">
name,year,active<br>
Maria,2024,true<br>
Jonas,2023,false
</div>
<div v-click style="font-size: 0.75em; color: #666; margin-top: 0.6em;">Tabellendaten, Exports, Datensammlungen</div>

</div>

</div>

<div v-click style="margin-top: 1.5em; padding: 1em; border-left: 3px solid #e8ff00; background: #0f0f0f; font-size: 0.82em; color: #aaa; line-height: 1.6;">
In meiner Praxis mit Datensätzen: fast alles startet als JSON oder CSV — und landet irgendwo als Visualisierung. Die Maschine übersetzt zwischen Formaten. Du musst verstehen, <em>was</em> da reist.
</div>

---

<div class="day-label">Tag 2</div>

# Rendering-Umgebungen

<div style="margin-top: 1em; color: #888; font-size: 0.85em; margin-bottom: 1.5em;">Wo läuft dein Code — und warum macht das einen Unterschied?</div>

<div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 1em;">

<div v-click class="paradigm-item" style="border-color: #2a2a5a;">
<div class="label" style="color: #7fb3ff;">Browser</div>
<div class="desc">JavaScript im Tab. Sieht den User. Hat Zugriff auf DOM, Klicks, Eingaben. Kein Zugriff auf dein Filesystem.</div>
</div>

<div v-click class="paradigm-item" style="border-color: #1a3a1a;">
<div class="label" style="color: #7fff7f;">Server</div>
<div class="desc">Läuft irgendwo auf einem Rechner im Internet. Sieht den User nicht direkt. Hat Zugriff auf Datenbanken, Files.</div>
</div>

<div v-click class="paradigm-item" style="border-color: #3a2a1a;">
<div class="label" style="color: #ffb347;">Terminal</div>
<div class="desc">Dein Rechner, direkt. Scripts, Tools, Build-Prozesse. Kein UI — nur Text.</div>
</div>

</div>

<div v-click style="margin-top: 1.5em; color: #e8ff00; font-size: 0.85em;">
Wenn das Modell sagt "du brauchst einen Backend-Server" — jetzt weißt du, was es meint.
</div>

---

<div class="day-label">Tag 2</div>

# Type Safety

<div style="margin-top: 1em; color: #888; font-size: 0.85em; margin-bottom: 1.5em; line-height: 1.6;">
Warum Typen existieren — und warum das Modell sie liebt.
</div>

<div style="display: grid; grid-template-columns: 1fr 1fr; gap: 1.5em;">

<div v-click>

**Ohne Typen (Python, JS):**
<div class="quiz-trap" style="font-size: 0.82em; margin-top: 0.8em;">
function add(a, b) {<br>
&nbsp;&nbsp;return a + b<br>
}<br><br>
add(1, 2)    // → 3 ✓<br>
add("1", 2)  // → "12" 💀
</div>

</div>

<div v-click>

**Mit Typen (TypeScript, Go, Rust):**
<div class="quiz-answer" style="font-size: 0.82em; margin-top: 0.8em;">
function add(a: number, b: number): number {<br>
&nbsp;&nbsp;return a + b<br>
}<br><br>
add("1", 2)  // → Fehler VOR dem Run ✓
</div>

</div>

</div>

<div v-click style="margin-top: 1.2em; color: #888; font-size: 0.82em; line-height: 1.5;">
Typen sind Verträge. Das Modell kann zuverlässigeren Code produzieren,<br>wenn es weiß, welche Form Daten haben sollen.
</div>

---

<div class="day-label">Tag 2</div>

# Environments

<div style="margin-top: 1em; color: #888; font-size: 0.85em; margin-bottom: 1.5em;">"Works on my machine" ist keine Entschuldigung.</div>

<div v-click class="quiz-trap" style="margin-bottom: 1em;">
Entwickler A: "Bei mir läuft's."<br>
Entwickler B: "Bei mir nicht."<br>
→ Unterschiedliche Node-Versionen, Betriebssysteme, Umgebungsvariablen.
</div>

<div v-click style="color: #888; font-size: 0.85em; margin-bottom: 1em; line-height: 1.6;">
Environments sind die unsichtbare Schicht: Welche Software ist installiert? Welche Versionen? Welche Variablen sind gesetzt? Was zeigt die KI-API als Key?
</div>

<div v-click class="quiz-answer" style="font-size: 0.82em;">
.env Datei:<br>
OPENAI_API_KEY=sk-...<br>
DATABASE_URL=postgres://...<br>
NODE_ENV=development
</div>

<div v-click style="margin-top: 1em; color: #e8ff00; font-size: 0.85em;">
API Keys, Secrets, Config — nie in den Code, immer in die Umgebung.
</div>

---
layout: section
---

<div class="day-label">Tag 2</div>

# Impulse von<br>Senior Devs.

---

<div class="day-label">Tag 2 / Peter</div>

# Spec-Driven Development

<div style="color: #555; font-size: 0.8em; letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 2em;">Peter · Senior Developer</div>

<div class="manifesto" style="max-width: 680px;">

<v-click>

Wie spezifiziert man ein Projekt so präzise, dass eine Maschine es **zuverlässig umsetzen kann**?

</v-click>

<v-click>

<div style="margin-top: 1.5em; padding: 1.2em; border-left: 3px solid #e8ff00; background: #0f0f0f; font-size: 0.9em; color: #aaa; line-height: 1.6;">
Nicht: "Mach mir eine App für Aufgabenverwaltung."<br><br>
Sondern: Ein strukturiertes Dokument, das Nutzergruppen, Datenmodell, Edge Cases, technische Constraints und Erfolgskriterien definiert — bevor eine Zeile Code geschrieben wird.
</div>

</v-click>

<v-click>

<div style="margin-top: 1.5em; color: #888; font-size: 0.85em; line-height: 1.6;">
Die Spec ist dein Steuerungsinstrument. Je präziser deine Anforderungen,<br>desto weniger Bullshit vom Modell.
</div>

</v-click>

</div>

---

<div class="day-label">Tag 2 / Esad</div>

# Advanced Agentic Coding

<div style="color: #555; font-size: 0.8em; letter-spacing: 0.1em; text-transform: uppercase; margin-bottom: 2em;">Esad · Senior Developer</div>

<div class="manifesto" style="max-width: 680px;">

<v-click>

**Vibe Coding**: Ein Prompt. Eine Antwort. Du reviewst. Du korrigierst.

</v-click>

<v-click>

**Agentic Coding**: Das Modell bekommt Werkzeuge — es liest Files, schreibt Code, führt Tests aus, korrigiert sich selbst.

</v-click>

<v-click>

<div style="margin-top: 1.5em; padding: 1.2em; border-left: 3px solid #e8ff00; background: #0f0f0f; font-size: 0.9em; color: #aaa; line-height: 1.6;">
Einen Prozess dirigieren, nicht einen Prompt.<br><br>
Du definierst das Ziel und die Grenzen — die Maschine navigiert den Weg.
</div>

</v-click>

<v-click>

<div style="margin-top: 1.2em; color: #ff6b35; font-size: 0.82em; line-height: 1.5;">
⚠ Mehr Autonomie = mehr Verantwortung. Der Kontext, den du setzt, entscheidet alles.
</div>

</v-click>

</div>

---
layout: center
---

<div class="day-label">Tag 2</div>

<div style="text-align: center;">

<div style="font-size: 2em; font-weight: 700; color: #e8ff00; line-height: 1.3;">
Prompt, Test,<br>Debug, Repeat.
</div>

<div v-click style="margin-top: 1.5em; color: #555; font-size: 0.85em; line-height: 1.8;">
Kontrollieren.<br>
Spezifizieren.<br>
Hinterfragen.<br>
</div>

<div v-click style="margin-top: 2em; color: #333; font-size: 0.75em; letter-spacing: 0.15em; text-transform: uppercase;">
Woche ist offen — Jonas ist dabei &nbsp;·&nbsp; Freitag: Hackathon
</div>

</div>

<!--
Ende Tag 2. Ab jetzt: freies Arbeiten mit Jonas. Ihr habt Projekte, ihr habt Kontext, ihr habt Werkzeuge.
-->
