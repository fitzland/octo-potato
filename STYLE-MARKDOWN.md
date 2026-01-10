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
-   **`###` (H3)**: Used for subsections within a major section, such as `### Icebreaker`, `### Core Message`, `### Lesson Flow`, `### Teaching Insights`, `### Scripture Reference`, `### Modern Application`, `### Discussion`.
-   **`####` (H4)**: Used for additional minor sections, such as `#### Common Answers`.

## 3. Admonitions

Use MkDocs-style admonitions to call out specific types of content. Admonitions can be standard (always open), collapsed by default, or expanded by default.

### Standard Admonitions (`!!!`)

Use the standard `!!!` syntax for primary content that should always be visible, such as scripture and discussion questions.

-   **`!!! quote`**: For Bible passages.
    -   The title should include the reference and translation (e.g., `"2 Kings 5:1-4, BSB"`).
    -   Place each verse on a new line.
    -   Make verse numbers bold (`**1**`).
-   **`!!! question`**: For discussion prompts.

**Example:**
```markdown
!!! question "Discussion"

    When have you seen God work through an unlikely person or in an unexpected way?
```

### Collapsed-by-Default Admonitions (`???`)

Use the `???` syntax for supplementary information that the reader can choose to expand. This is ideal for tangential context or deeper dives.

-   **`??? info`**: For "read more" sections or supplementary context.

**Example:**
```markdown
??? info "Read More. Powerful & Powerless"

    Naaman was a man who had it all...
```

### Expanded-by-Default Admonitions (`???+`)

Use the `???+` syntax for important notes or application sections that should be visible by default but can be collapsed by the user to reduce clutter.

-   **`???+ note`**: For further insights or contextual notes.
-   **`???+ success`**: For supplementary application principles (e.g., "Servant Girl Principle").
-   **`???+ warning`**: For supplementary cautionary tales or negative examples (e.g., "Gehazi's Deception").

**Example:**
```markdown
???+ success "Application. Servant Girl Principle"

    God often places us in hard places so that we can be His witness there.
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

## 7. Lesson-Specific Elements

These rules apply to specific components within Bible study lessons.

### Core Message
-   The Core Message must be a single, bold, tweetable sentence.
-   **Example**: `**God restores us as we are obedient to Him, and His methods often defy our expectations and humble our pride**.`

### Lesson Flow
-   Each item in the "Lesson Flow" list should follow the format: `1. **Movement Title**. One-sentence description`.
-   Each item (Movement Title) in the "Lesson Flow" should be linked to the related lesson section.
-   **Example**: `1. [**Unlikely Hope**. A servant girl points the way](#1-unlikely-hope)`

### Movement Taglines
-   Movement taglines should be bold and end with a period outside the bolding.
-   **Example**: `**Hope arrives from the most unexpected source**.`

### Common Answers
-   Primary answers should be a bold, capitalized phrase followed by an explanation, ending with a period outside the bolding.
-   Follow-up probes should be italicized.
-   **Example**:
    ```markdown
    **Pride**. fear of losing image
    - *follow-up*. pushing for more insight or depth
    ```

### Modern Application
-   Modern application sections should be short, piercing, and memorable (up to three punchy lines).

### Weekly Challenge Titles
-   Weekly challenge titles should be bold and end with a period outside the bolding.
-   **Example**: `1. **Challenge Title**. short, concrete, doable this week`