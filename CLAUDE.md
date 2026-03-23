# fitzhugh.us — Bible Study Notes Project

## Project Overview

MkDocs site (Material theme) containing Bible study lessons, book notes, and technical documentation. Primary content is expository adult Bible study lessons organized by series.

## Active Series

| Series | File prefix | Series name (front matter) |
|---|---|---|
| Elisha | `elisha-` | `Elisha Series` |
| Matthew 5 | `matt05-` | `Matthew 5 Series` |
| Risk Takers | `risk-` | `Risk Series` |
| Character Counts | `character-` | `Character Series` |
| Limited Resources | `resources-` | `Limited Resources, Limitless God` |
| Life's Interruptions | `interruptions-` | `Life's Interruptions` |

## Front Matter Standard

All docs files use this front matter structure:

```yaml
---
front_matter_title: [Title]
tags:
    - [OT or NT]
    - [Book name]
    - [Theme or character]
series: [Series name]
scripture: [Primary passage, e.g. "Matthew 5:13-16"]
document_type: [notes | sermon | sermon-script | book-notes | technical | page]
status: [draft | published]
modified_date: YYYY-MM-DD
presented_date: YYYY-MM-DD   # Bible study lessons only
---
```

## Markdown Style Guide for Bible Study Lessons

Source: `task-bible-study-format.md`

### Headings

- `#` H1 — main lesson title only
- `##` H2 — major sections (`## Introduction`, `## Closing`, section titles). No numeric prefixes.
- `###` H3 — subsections: `### Series Overview` (before Icebreaker, when present), `### Icebreaker`, `### Core Message`, `### Scripture...`, `### Context & Insights`, `### [Topic] (Discussion:Mind)`, `### [Topic] (Reflection:Heart)`, `### Decision (Will)`, `### Challenges (Practice)`, `### Prayer`
- `####` H4 — not currently used
- Never skip heading levels.
- No leading articles in H3 headings — do not begin with "The", "A", or "An". Write `Dried Brook` not `The Dried Brook`.

### Scripture Passages

- Main reference after H1 title: plain text, no admonition.
- Inline passages: `###` heading with reference and translation, blockquote for text, bold verse numbers.

```markdown
### 1 Samuel 17:32-37, BSB

> **32** And David said to Saul...
```

- Verse references in body text: `v.8` (single), `vv.9-10` (range), `vv.8,10,12` (multiple). No spaces.

### Lesson Prompts

**Discussion (Mind)** — descriptive `###` heading with `(Discussion:Mind)` label, question in `>` blockquote, anticipated answers with bolded label outside bold:

```markdown
### Past Experiences (Discussion:Mind)

> *What* exactly did the father ask the disciples to do?

**Heal My Son**. The father asked the disciples to heal his son, but they failed.
```

**Reflection (Heart)** — descriptive `###` heading with `(Reflection:Heart)` label, question in `>`:

```markdown
### Lions & Bears (Reflection:Heart)

> *How* has God delivered you in the past?
```

**Decision (Will)** — `### Decision (Will)` heading, bold paragraph headers, no bullets:

```markdown
### Decision (Will)

**Warrior's Declaration**. Are you ready to confront your giant?
```

**Challenges (Practice)** — `### Challenges (Practice)` heading, bold paragraph headers, max 4, last is always memory verse:

```markdown
### Challenges (Practice)

**Resume of Faith**. Start a Faith Journal this week.

**Memory Verse**. 1 Samuel 17:47. *For the battle is the LORD's.*
```

### Other Formatting Rules

- **Punctuation**: outside bold/italic (`**Key Point**.` not `**Key Point.**`)
- **Italics**: key theological terms, Greek transliterations, emphasis in questions, interrogatives (*What*, *Why*, *How*, *When*, *Where*)
- **Core Message**: single sentence, not bold
- **Transitions**: italicized (`*Transition*. [Bridge sentence]`)
- **Icebreakers**: multiple questions under single `### Icebreaker` heading, each in a blockquote, followed by `**Synthesis**. [paragraph]`

### Pedagogical Rules

- Socratic priority: convert interpretive points into Observe & Discuss (Mind) questions
- Include [bracketed possible answers] as teacher safety net (not read aloud unless needed)
- All interpretive content delivered via questions — no "Key Insights" bullet dumps
- Progression must flow: observe → interpret → reflect → apply

## Available Skills

| Command | Purpose |
|---|---|
| `/bs-new` | Prepare a new lesson from scratch |
| `/bs-revise` | Supplement an existing lesson via Biblehub |
| `/bs-walkthrough` | Simulate a live teaching session |
| `/bs-refine` | Audit and improve the system |
