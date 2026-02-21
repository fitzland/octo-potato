# Markdown Style Guide

This document outlines the simplified Markdown styling conventions for all Bible study lessons, designed for clarity, consistency, and repeatability. These rules supersede any previous style guides.

---

## 1. Headings

Follow a strict hierarchical structure for headings. **Never skip levels** (e.g., an `H1` must be followed by an `H2`, not an `H3`).

-   `#` (H1): The main lesson title.
-   `##` (H2): Major sections (e.g., `## Section Title`), `## Introduction`, and the `## Closing` section. Do not use numeric prefixes for section titles.
-   `###` (H3): Subsections like `### Icebreaker`, `### Core Message`, `### Scripture...`, `### Discussion`, and `### Reflection (Heart)`.
-   `####` (H4): Not currently used.

---

## 2. Scripture Passages

The main scripture reference at the top of the lesson (after the H1 title) should be plain text.

Scripture passages **within** each lesson section **must not** use `!!! quote` admonitions. The correct format is a Level 3 heading followed by a blockquote.

-   Use a `###` heading with the reference and translation (e.g., `### 1 Samuel 17:32-37, BSB`).
-   Use a markdown blockquote (`>`) for the text.
-   Make verse numbers bold (`**32**`).
-   When referencing specific verses in discussion or insights, use the format `v.11` (no space).

**Example:**
```markdown
### 1 Samuel 17:32-37, BSB

> **32** And David said to Saul, “Let no man’s heart fail on account of this Philistine. Your servant will go and fight him!”
```

---

## 3. Lesson Prompts

There are four distinct types of prompts. They **must not** use `!!! question` admonitions or other complex formatting.

### Icebreakers

-   Group multiple icebreaker questions under a single `### Icebreaker` heading.
-   Use blockquotes for each question.
-   Include a synthesis paragraph at the end of the introduction, formatted as `**Synthesis**. Text`.

### Discussion Questions

Each discussion prompt should be under its own descriptive, topical Level 3 heading.

-   Use a descriptive `###` heading that states the topic in the format `### Topic (Discussion:Mind)` (e.g., `### Nature of Giants (Discussion:Mind)`).
-   Place the question(s) inside a markdown blockquote (`>`).
-   Anticipated answers should follow the question. Format them with a bolded label followed by a period **outside** the bolding.

**Example:**
```markdown
### Nature of Giants (Discussion:Mind)

> How did David's private faithfulness in the pasture prepare him for his public battle in the valley?

**Private Victories, Public Confidence**. God often tests and proves our faith in small, private battles before He calls us to larger, public ones.
```

### Reflection Questions

-   Use a descriptive `###` heading that states the topic in the format `### Topic (Reflection:Heart)` (e.g., `### Personal Audit (Reflection:Heart)`).
-   Place the question directly below the heading in a blockquote.

**Example:**
```markdown
### Personal Audit (Reflection:Heart)

> How has God delivered you or shown His faithfulness in the past? What are some *lions and bears* that He has defeated?
```

### Decision Questions

-   Use a `### Decision (Will)` heading.
-   Present questions as bolded paragraph headers without bullets.

**Example:**
```markdown
### Decision (Will)

**Warrior's Declaration**. Are you ready to confront your giant, not with your own strength, but *in the name of the LORD of Hosts*?

**Ultimate Motive**. Is your desire to win your battle for your own relief, or so that others will know *that there is a God in Israel*?
```

### Challenges (Practice)

-   Use a `### Challenges (Practice)` heading.
-   Present challenges as bolded paragraph headers without numbers.
-   Never more than four total challenges.
-   The last challenge should be a memory verse challenge, formatted as `**Memory Verse**. Reference. *Text of verse.*`

**Example:**
```markdown
### Challenges (Practice)

**Resume of Faith**. Start a *Faith Journal* this week. Write down one thing God has done for you.

**Memory Verse**. 1 Samuel 17:47. *For the battle is the LORD's, and He will give you into our hands.*
```

---

## 4. Other Formatting Rules

-   **Emphasis and Punctuation**: Punctuation for insight labels and paragraph headers should be placed **outside** of bold or italic formatting (e.g., `**Key Point**.`).
-   **Italics**: Use italics extensively for key theological terms, emphasis within questions, and Greek transliterations (e.g., *guard*, *learned*, *autarkēs*).
-   **Core Message**: The single-sentence Core Message should not be bold.
-   **Transitions**: Brief transition statements between sections should be italicized.
