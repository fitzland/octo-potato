# Markdown Style Guide

This document outlines the simplified Markdown styling conventions for all Bible study lessons, designed for clarity, consistency, and repeatability. These rules supersede any previous style guides.

---

## 1. Headings

Follow a strict hierarchical structure for headings. **Never skip levels** (e.g., an `H1` must be followed by an `H2`, not an `H3`).

-   `#` (H1): The main lesson title.
-   `##` (H2): Major sections (e.g., `## 1. Section Title`), `## Introduction`, and the `## Closing` section.
-   `###` (H3): Subsections like `### Icebreaker`, `### Core Message`, `### Scripture...`, `### Discussion`, and `### Reflection (Heart)`.
-   `####` (H4): Used only for `#### Common Answers` subsections.

---

## 2. Scripture Passages

The main scripture reference at the top of the lesson (after the H1 title) should be plain text.

Scripture passages **within** each lesson section **must not** use `!!! quote` admonitions. The correct format is a Level 3 heading followed by a blockquote.

-   Use a `###` heading with the reference and translation (e.g., `### 1 Samuel 17:32-37, BSB`).
-   Use a markdown blockquote (`>`) for the text.
-   Make verse numbers bold (`**32**`).

**Example:**
```markdown
### 1 Samuel 17:32-37, BSB

> **32** And David said to Saul, “Let no man’s heart fail on account of this Philistine. Your servant will go and fight him!”
```

---

## 3. Lesson Prompts

There are four distinct types of prompts. They **must not** use `!!! question` admonitions or other complex formatting.

### Discussion Questions

-   Use a descriptive Level 3 heading that states the topic of the question (e.g., `### Nature of Giants`).
-   Place the question(s) inside a markdown blockquote (`>`).
-   If providing anticipated answers, use a `#### Common Answers` subheading.

**Example:**
```markdown
### Nature of Giants

> How did David's private faithfulness in the pasture prepare him for his public battle in the valley?

#### Common Answers

**Private Victories, Public Confidence**. God often tests and proves our faith in small, private battles before He calls us to larger, public ones.
```

### Reflection (Heart) Questions

-   Use a `### Reflection (Heart)` heading.
-   Place the question directly below the heading in a blockquote.

**Example:**
```markdown
### Reflection (Heart)

> How has God delivered you or shown His faithfulness in the past? What are some *lions and bears* that He has defeated?
```

### Decision (Will) Questions

-   Use a `### Decision (Will)` heading.
-   Present questions as a bulleted list. Each question should be a bolded phrase or sentence.

**Example:**
```markdown
### Decision (Will)

- **Warrior's Declaration**. Are you ready to confront your giant, not with your own strength, but *in the name of the LORD of Hosts*?
- **Ultimate Motive**. Is your desire to win your battle for your own relief, or so that others will know *that there is a God in Israel*?
```

### Challenges (Practice)

-   Use a `### Challenges (Practice)` heading.
-   Present challenges as a numbered list. Each item should have a bolded title.
-   Never more than four total challenges.
-   The last challenge should be a memory verse challenge.

**Example:**
```markdown
### Challenges (Practice)

**1. Resume of Faith**. Start a *Faith Journal* this week. Write down one thing God has done for you.

**2. Memory Verse**. Memorize [Reference] — "[Full text of verse]"
```

---

## 4. Other Formatting Rules

-   **Emphasis and Punctuation**: Punctuation should be placed **outside** of bold or italic formatting (e.g., `**Key Point**.` not `**Key Point.**`).
-   **Core Message**: The single-sentence Core Message should not be bold.
-   **Transitions**: Brief transition statements between sections should be italicized.
