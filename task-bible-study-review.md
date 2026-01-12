# Task: Review Bible Study Lesson

This document outlines the instructions for reviewing and improving an existing bible study lesson.

## Goal

The primary goal is to enhance a bible study lesson by comparing it with an external chapter summary from Biblehub and suggesting improvements that enrich the content without altering its core message.

## Inputs

1.  **Bible Lesson File:** The path to the markdown file of the bible study lesson to be reviewed.
2.  **Bible Passage:** The specific bible book and chapter the lesson is based on (e.g., Genesis 1).

## Process

1.  **Identify Key Information:** From the user's request or the lesson file itself, determine the Bible book and chapter number.

2.  **Construct Biblehub URL:** Create the URL for the corresponding chapter summary on Biblehub using the following format:
    `https://biblehub.com/chaptersummaries/[BibleBook]/[BibleChapter].htm`
    - Replace `[BibleBook]` with the name of the bible book (e.g., `genesis`).
    - Replace `[BibleChapter]` with the chapter number (e.g., `1`).
    - Note: The book name in the URL should be lowercase.

3.  **Fetch External Content:** Use the `web_fetch` tool to retrieve the summary from the constructed Biblehub URL.

4.  **Read Lesson Content:** Use the `read_file` tool to read the entire content of the bible study lesson markdown file.

5.  **Analyze and Compare:**
    - Carefully read both the Biblehub chapter summary and the existing lesson content.
    - Identify the core message, key themes, and structure of the existing lesson.
    - Look for supplementary information in the Biblehub summary that could enhance the lesson. This may include:
        - Historical context.
        - Deeper insights into key characters or events.
        - Cross-references to other scriptures.
        - Alternative interpretations or points of emphasis.
        - Key theological concepts.

6.  **Formulate Suggestions:**
    - Based on the comparison, develop specific, actionable suggestions for improving the lesson.
    - **Crucially, ensure all suggestions align with and support the existing core message of the lesson.** The goal is to enrich, not to change the fundamental focus.
    - Frame suggestions clearly. For example: "In the 'Introduction' section, you could add a brief note on the historical context of...' or "The Biblehub summary mentions [insight]. We could add a discussion question about this, such as: '...?'"

7.  **Present Suggestions:**
    - Present the formulated suggestions to the user for review.
    - Do not modify the lesson file directly. Wait for the user's feedback and approval before applying any changes.
