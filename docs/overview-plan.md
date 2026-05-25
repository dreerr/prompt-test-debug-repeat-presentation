# Prompt, Test, Debug, Repeat – Wochenübersicht

---

## Dienstag – Grundlagen & Werkzeuge

### Eröffnung
- **Modalitäten:** Anwesenheitspflicht, Eintrag in Anwesenheitsliste via Discord, max. 1 Fehltag
- **Wochenplan:** Überblick über alle 5 Tage, Ziele, Erwartungen an die Gruppe
- **Vorstellungsrunde** (strukturiert): Was will ich diese Woche schaffen? Was interessiert mich nicht? Welche LLM-Tools nutze ich, wo hab ich Accounts? Was hab ich schon mit Vibe Coding gemacht?

### Übung: Prompting ohne Computer
Nur Zettel & Stift. Aufgabe: Mit dem Sitznachbar eine Animation beschreiben, die an der Tafel gepromptet werden könnte. Ziel: Präzision und Vollständigkeit von Prompts erfahren, bevor man den Computer aufmacht.

---

*Pause*

---

### Frontaleinheit I: KI verstehen

**Prompting für Coding-Agenten**

- **Kontext vor Aufgabe:** Erkläre zuerst was das Projekt ist, was bereits existiert, was das Ziel ist – dann erst die konkrete Aufgabe. Das Modell braucht den Rahmen.
- **Bekannte Frameworks benennen:** Sag "mach das mit Tailwind" oder "verwende vanilla JavaScript" – nicht "mach es schön". Bekannte Namen reduzieren Interpretationsspielraum.
- **Screenshots und Beispiele mitgeben:** Ein Bild des gewünschten Ergebnisses, eine URL, ein Referenz-Screenshot – das ist oft präziser als Worte.
- **Weder zu vage noch zu over-specific:** "Mach eine Webseite" ist zu offen. Aber 10 Anforderungen auf einmal überfordern das Modell genauso. Eine klare Hauptaufgabe, 2–3 Constraints.
- **Erwartetes Ergebnis beschreiben, nicht den Weg:** "Ich will dass beim Klick auf den Button die Farbe wechselt" – nicht "ändere die onClick-Funktion in Zeile 42 so dass...". Den Weg findet das Modell selbst.
- **Negative Constraints explizit:** "Ohne externe Libraries", "keine neuen Dateien anlegen", "ändere nichts am bestehenden CSS" – was nicht passieren soll, muss gesagt werden.

**Was können LLMs gut / schlecht?**

| Gut | Schlecht |
|---|---|
| Boilerplate & Standardmuster | Logik über viele Schritte verfolgen |
| Erklären & kommentieren | Zählen, rechnen, exakt zitieren |
| Varianten generieren | Eigene Fehler erkennen |
| Debugging mit Fehlermeldung | Den Überblick in langen Projekten behalten |
| Umformulieren & übersetzen | Wissen nach Trainings-Cutoff |

**Context Window**
- Was ist ein Context Window? (Kurzzeitgedächtnis der KI für eine Session)
- Was ist drin: Systemprompt, Gesprächshistorie, geöffnete Dateien, Fehlermeldungen, Ergebnisse von Tool Calls
- Warum relevant: Wenn das Window voll ist oder zu viel Irrelevantes enthält, degradiert die Qualität; neue Konversation = sauberer Neustart
- Praktische Konsequenz: kurze Sessions, gezielter Kontext, nicht alles in eine Konversation

**Weitere KI-Grundlagen (Schnelldurchlauf)**
- Halluzinationen: das Modell erfindet zuversichtlich – Output immer testen, nie blind vertrauen
- Modellunterschiede: nicht alle LLMs gleich stark, Kontext-Größe und Fähigkeiten variieren
- Token & Kosten: was sind Tokens, warum sind sie relevant für Usage-Limits und API-Kosten

---

*Pause*

---

### Frontaleinheit II: Programmieren verstehen

**Begriffsklärung (technikfern)**

| Begriff | Kurzerklärung |
|---|---|
| **Markup** (HTML) | Beschreibt Struktur und Inhalt – kein Programm, keine Logik, nur "was ist was" |
| **Skriptsprache** (JavaScript, Python) | Gibt Anweisungen, die ausgeführt werden; läuft zur Laufzeit |
| **Programmiersprache** (C, Rust) | Wird vor Ausführung kompiliert; direkter Zugriff auf Hardware |
| **Frontend** | Alles, was im Browser des Users läuft und sichtbar ist |
| **Backend** | Läuft auf einem Server, nicht sichtbar; Logik, Daten, Authentifizierung |
| **Server** | Ein Computer, der dauerhaft läuft und auf Anfragen wartet |
| **Client** | Das Gerät/Programm, das Anfragen stellt (z.B. der Browser) |
| **API** | Definierte Schnittstelle zwischen zwei Systemen; "Wie rede ich mit X?" |
| **Library** | Fertige Codesammlung für eine bestimmte Aufgabe |
| **Package** | Verteilungsformat für Libraries; wird via Package-Manager installiert |

---

**Orientierungskarte: Paradigmen, die du kennen solltest**

Nicht als Lernziel – als Kontext. Wenn das Modell sagt "dafür brauchst du einen Backend-Server", solltest du wissen, was das bedeutet und was es impliziert.

**Version Control mit Git**
Beispiel: zwei Personen ändern dieselbe Datei – was passiert? Git trackt jede Änderung, wer sie gemacht hat, wann. Kein `_final_wirklichFinal.html` mehr.

**Package Management**
Beispiel: `npm install` lädt eine Library herunter und macht sie im Projekt verfügbar. Das Modell schreibt `import X from 'Y'` – woher kommt Y? Aus dem Package-Manager.

**APIs und wie man mit ihnen kommuniziert**
Beispiel: Wetter-App fragt einen Wetter-Server per HTTP-Request an, bekommt JSON zurück, zeigt es an. Das ist eine API. Du brauchst meist einen Key – und damit ein Konto, Kosten, Rate Limits.

**Type Safety**
Beispiel: `"5" + 5` ergibt in JavaScript `"55"`, in Python einen Fehler. Maschinen brauchen eindeutige Typen; Menschen denken implizit. Typisierte Sprachen erzwingen Klarheit – das Modell wählt manchmal typed, manchmal nicht, du solltest den Unterschied kennen.

**Compiled vs. Interpreted**
Beispiel: Python-Script läuft direkt; ein C-Programm muss erst gebaut werden, bevor es läuft. Relevant wenn das Modell sagt "du musst das erst kompilieren."

**Rendering Environments**
Beispiel: JavaScript läuft im Browser (Frontend), aber auch auf dem Server (Node.js) und im Terminal. Derselbe Code, drei verschiedene Kontexte – nicht jede Library funktioniert überall.

**Datenformate: JSON & CSV**
Beispiel: JSON ist was zwischen Systemen reist – `{"name": "Anna", "age": 24}`. CSV ist tabellarisch – Spreadsheet als Textdatei. APIs antworten meist mit JSON; Daten-Exports oft als CSV.

**Environments & "Works on my machine"**
Beispiel: Das Projekt läuft lokal, aber nicht beim Kommilitonen – weil eine Library fehlt, die du nie explizit installiert hast, weil sie schon da war. Environments (`.env`-Files, `requirements.txt`, `package.json`) lösen das durch explizite Deklaration aller Abhängigkeiten.

**VS Code – Interface-Einführung**
- **Explorer** (links): Datei- und Ordnerstruktur des Projekts
- **Editor** (Mitte): Dateien bearbeiten; Tabs für mehrere offene Dateien
- **Terminal** (unten): Shell direkt in VS Code; wichtigste Arbeitsfläche
- **Source Control** (links, Git-Icon): Änderungen sehen, committen, pushen
- **Extensions** (links): Erweiterungen installieren
- **Command Palette** (`Cmd/Ctrl+Shift+P`): Alles per Tastatur erreichbar
- **GitHub Copilot einrichten:** Extension installieren, mit GitHub-Account verbinden, Chat-Panel öffnen

**Shell Basics** *(mit praktischem Teil)*
- `cd ordnername` / `cd ..` – Navigation
- `ls` / `dir` – Inhalt anzeigen
- `node datei.js` / `python datei.py` – Programm ausführen
- **Tab** – Autocomplete für Datei- und Ordnernamen
- **↑ / ↓** – letzte Befehle wiederholen
- Übung: Von Home-Verzeichnis in einen bestimmten Projektordner navigieren, Skript ausführen

**Version Control**
- Warum: kein `_final`, `_finalLast`, `_wirklichFinal` – Git ist die Zeitmaschine
- Begriffe: Repository, Commit, Branch, Push, Pull, Merge, Konflikt
- In VS Code: Source Control Panel; Änderungen stagen, Commit-Message schreiben, pushen
- Verbindung zu GitHub: Repo erstellen, lokal klonen oder lokales Repo pushen

---

*Pause*

---

### Erste Gehversuche: GitHub Copilot *(in Paaren)*
- Chat vs. Inline-Completion vs. Edits-Modus: wann was?
- Agent Mode: was kann er, was nicht
- Usage Tokens: was sind sie, wie viel hat man, was kostet was
- Aufgabe: Eine einfache HTML-Seite gemeinsam per Copilot bauen – mit dem Ziel, den Loop zu verstehen: Prompt → Output → Test → Korrektur

---

## Mittwoch – Methoden & Konzeption

### Impulsvorträge (je ~15 min + Fragen)
- **Philipp:** Einblicke in Setup und Workflow
- **Esad:** Advanced Agentic Coding – wie Agenten in der Praxis arbeiten
- **Offene Fragerunde**

---

*Pause*

---

### Methodik: Von der Idee zum Projekt

**PRD – Product Requirements Document**
- Was ist ein PRD, warum schreiben wir eines bevor wir promoten?
- Struktur: Ziel, Zielgruppe, Features (Must/Should/Could), Nicht-Ziele
- Übung: Eigenes Projekt als Mini-PRD formulieren (1 Seite)

**Spec-Driven Development & Acceptance Criteria**
- Spec als Grundlage für Prompts: klarer Input → vorhersehbarerer Output
- Acceptance Criteria: "Das Feature ist fertig wenn..." – konkrete, testbare Bedingungen
- Feedback-Loop einbauen: wann teste ich, wann committe ich, wann starte ich neu?

**Weitere Copilot-Übungen**
- Was funktioniert gut mit Chat, was mit Inline, was mit Agent?
- Typische Fallstricke: zu langer Kontext, zu vage Prompts, fehlende Specs

**Gruppenfindung & Ideenentwicklung**
- Brainstorming: jede*r pitcht 1–2 Ideen (2 min je)
- Gruppen finden sich nach Interesse und Kompatibilität
- Ideen vorstellen im Plenum
- Check-in: Ist die Idee in 2–3 Tagen machbar? Complexity-Check mit dem Instructor

---

## Donnerstag & Freitag – Projektarbeit

### Struktur (täglich)
- **Morgens:** Kurzes Standup pro Gruppe (Was ist der Plan für heute? Wo stecken wir?)
- **Hauptblock:** Selbstständige Projektarbeit; Instructor zirkuliert, greift nur auf Nachfrage ein oder bei offensichtlichem Hänger (>20 min ohne Fortschritt)
- **Zwischenstand Do-Nachmittag:** Jede Gruppe zeigt kurz Stand, bekommt Feedback; Scope ggf. anpassen
- **Abschluss:** Kurze Tagesreflexion in der Gruppe

### Instructor-Fokus
- Wer testet inkrementell, wer baut blind?
- Wer beschreibt Fehler präzise, wer sagt "funktioniert nicht"?
- Wer startet bei Sackgassen neu, wer kämpft?
- Scope-Creep aktiv unterbrechen: "Was ist die kleinste Version, die die Idee zeigt?"

---

## Samstag – Abschluss & Präsentation

### Polishing & Deployment
- Letzter Build-Block: nur Bugfixes und Finish, keine neuen Features
- Deployment: Single-HTML → GitHub Pages / Netlify Drop; komplexere Projekte je nach Stand
- Jonas on standby für technische Deployment-Probleme

### Präsentationen
- Format: ~5 min pro Gruppe
  - Was habt ihr gebaut?
  - Live-Demo
  - Was hat funktioniert, was nicht?
  - Was würdet ihr nächste Woche angehen?
- Keine Slides nötig – das Ding läuft oder es läuft nicht

### Preisverleihung
- Kategorien noch zu definieren (z.B. "mutigster Scope", "eleganteste Lösung", "best recovery from disaster")

### Abschluss
- Offene Reflexionsrunde
- Ressourcen & Next Steps
- Feedback

---

Ein paar Optionen – du kannst picken was passt:

---

### Puffer-Aktivitäten

**"Was ist hier schiefgelaufen?"** – kaputten Code oder einen gescheiterten Copilot-Verlauf anschauen und gemeinsam diagnostizieren. Kein Lösen, nur Benennen. Schult den Blick ohne Erfolgsdruck.

**Reverse Engineering** – ein fertiges kleines Projekt (HTML-Datei) aufmachen, ohne Erklärung. Aufgabe: Was tut das? Wie ist es gebaut? Was würde brechen wenn man X ändert? Funktioniert gut in Paaren.

**Prompt-Battle** – beide schreiben unabhängig einen Prompt für dieselbe Aufgabe, beide Outputs vergleichen. Diskussion: Was hat welche Version besser gemacht, warum?

**"Was kann ich in 20 Minuten bauen?"** – freies Mini-Experiment ohne Anspruch, nichts muss fertig werden. Gut als Ventil nach einem langen Frontal-Tag.

**Kontextfenster-Experiment** – bewusst eine Konversation bis zur Degradierung führen: immer mehr rein, beobachten wann und wie die Qualität kippt. Macht das abstrakte Konzept vom Dienstag erfahrbar.

**Stille Reflexion + Discord-Post** – jede*r schreibt 5 min was sie heute gelernt haben und postet es in einen Workshop-Channel. Gibt dir als Instructor einen guten Überblick wo die Gruppe steht, ohne Plenum.
