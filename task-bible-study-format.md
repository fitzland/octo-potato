# Task: Format Bible Study Lesson

This task focuses on auditing and applying the standard formatting and structural rules to an existing Bible study lesson. You act as a meticulous editor ensuring every element aligns with the project's specific Markdown conventions.

## Goals

- **Structural Alignment**: Ensure the lesson follows the hierarchy defined in `STRUCTURE-BIBLE-LESSON.md`.
- **Formatting Consistency**: Apply the specific styling rules from `style-bible-study.md` (headings, blockquotes, bolding, italics).
- **Metadata Quality**: Ensure YAML frontmatter is present and accurate.
- **Tone & Clarity**: Verify that punctuation is outside of bolding/italics and that theological terms are properly emphasized.

---

## Core Workflow

### Phase 1: Structural Audit

1. **Verify Headings**: Check that H1, H2, and H3 levels are used correctly and no levels are skipped.
2. **Check Section Flow**: Ensure the lesson contains an Introduction, Core Message, 2-4 Teaching Sections, and a Closing.
3. **Validate Components**: Confirm that each teaching section has:
    - Scripture (H3 + blockquote)
    - Context & Insights (bullets with bold labels)
    - Discussion (H3 with `(Discussion:Mind)`)
    - Reflection (H3 with `(Reflection:Heart)`)
    - Transition (Italicized)

### Phase 2: Apply Formatting Rules

1. **Scripture Formatting**:
    - Ensure verse numbers are bold (`**32**`).
    - Verify references use the format `### Book Chapter:Verses, BSB`.
    - Convert any `!!! quote` admonitions to standard blockquotes.
2. **Prompt Formatting**:
    - **Icebreakers**: Group under `### Icebreaker` using blockquotes. Ensure a `**Synthesis**.` paragraph exists.
    - **Discussion**: Ensure headings use the `### Topic (Discussion:Mind)` format. Questions in blockquotes.
    - **Reflection**: Ensure headings use the `### Topic (Reflection:Heart)` format. Questions in blockquotes.
    - **Decision**: Ensure headings use `### Decision (Will)`. Questions as bolded paragraph headers.
    - **Challenges**: Ensure headings use `### Challenges (Practice)`. Challenges as bolded paragraph headers.
3. **Punctuation & Emphasis**:
    - Move periods/colons outside of bolding (e.g., `**Key Point**.`, not `**Key Point.**`).
    - Italicize key theological terms and emphasis within questions.
    - Ensure the Core Message is *not* bold.

### Phase 3: Metadata & Frontmatter

1. **YAML Block**: Ensure a valid YAML frontmatter block exists with `title` and `tags`.
2. **Tag Consistency**: Use title-cased tags (e.g., `OT`, `NT`, `Gospels`, `Elisha`).

---

## Key Guidelines

- **No Admonitions**: Do not use `!!!` style admonitions for questions or scripture.
- **Reference Style**: Use `v.11` for specific verse references within the text.
- **Memory Verse**: Ensure the final challenge is the memory verse formatted as: `**Memory Verse**. Reference. *Text of verse.*`
- **Prayer**: Ensure the closing prayer is in a blockquote with multiple paragraphs.

---

## Standard Reference Files

- `style-bible-study.md`: Detailed formatting rules.
- `STRUCTURE-BIBLE-LESSON.md`: Structural template.
