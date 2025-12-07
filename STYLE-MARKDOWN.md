# Markdown Style Guide

This document outlines the Markdown styling conventions for our project, designed for clarity and consistency, especially for output with MkDocs.

## 1. Frontmatter

Every document should begin with a YAML frontmatter block.

-   **tags**: Include relevant tags such as the testament (OT/NT), biblical section (e.g., HISTORY), book name, and key figures or themes.
-   **title**: Provide a clear, descriptive title for the document.

**Example:**
```yaml
---
tags:
    - OT
    - HISTORY
    - 2 Kings
    - Elisha
title: God's Hand in Restoring Lives
---
```

## 2. Headings

Follow a strict hierarchical structure for headings. **Never skip levels** (e.g., an `H1` must be followed by an `H2`, not an `H3`). Avoid colons in headings unless explicitly introducing a list or example.

-   **`#` (H1)**: Reserved for the main document title. This should match the `title` in the frontmatter.
-   **`##` (H2)**: Used for major sections of the document, such as main movements (`## 1. First Movement Title`). Also used for `## Closing Reflection (Moment of Decision)`, `## Postscript`, and `## Additional Reference`.
-   **`###` (H3)**: Used for subsections within a major section, such as `### Icebreaker`, `### Core Message`, `### Lesson Flow`, `### Teaching Insights`, `### Common Answers`, `### Modern Application`.

## 3. Admonitions

Use MkDocs-style admonitions to call out specific types of content.

### Scripture Quotes

Use the `!!! quote` admonition for Bible passages.

-   The title should include the reference and translation (e.g., `"2 Kings 5:1-4, BSB"`).
-   Place each verse on a new line.
-   Make verse numbers bold (`**1**`).

**Example:**
```markdown
!!! quote "2 Kings 5:1-4, BSB"

    **1** Now Naaman...
    **2** At this time...
```

### Discussion Questions

Use the `!!! question` admonition for discussion prompts.

**Example:**
```markdown
!!! question "Discussion"

    When have you seen God work through an unlikely person or in an unexpected way?
```

## 4. Emphasis and Punctuation

Punctuation should always be placed **outside** of any bold or italic formatting to maintain clean styling.

-   **Correct**: `**Key Insight**.`, `*powerless*.`
-   **Incorrect**: `**Key Insight.**`, `*powerless.*`

This applies to labels, titles, and emphasized words within a sentence.

**Examples:**
- `**Option A**. When have you...`
- `The question is never *Why am I here?* but...`

## 5. Lists

When creating bulleted or numbered lists, ensure there is a blank line between each list item. This prevents them from being rendered as a single, run-on paragraph.

**Example:**
```markdown
- First item.

- Second item.

- Third item.
```

## 6. Minimal Formatting

Exercise restraint with formatting. Use bold and italics only when they add significant punch or clarity. Avoid over-formatting the text.
