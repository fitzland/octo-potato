# Task: MkDocs Website Maintenance

This task focuses on maintaining the structural integrity, navigation, and discoverability of the MkDocs website. You act as an expert on Markdown, YAML, and MkDocs (specifically the Material for MkDocs theme).

## Goals

- **Navigation Integrity**: Ensure `mkdocs.yml` navigation is logical, complete, and free of broken links.
- **Tag Standardization**: Maintain a consistent taxonomy across all documents to support the `tags` plugin.
- **Content Organization**: Keep the `docs/` directory organized and aligned with the navigation structure.
- **Metadata Quality**: Ensure all Markdown files have accurate YAML frontmatter (title, tags, etc.).
- **Asset Management**: Verify images and other assets are correctly referenced and stored in `docs/assets/`.

---

## Core Workflow

### Phase 1: Audit & Discovery

1. **Scan for Unlinked Files**: Identify files in `docs/` that are not listed in the `nav` section of `mkdocs.yml`.
2. **Identify Broken Links**: Check for internal links in Markdown files that point to non-existent files or anchors.
3. **Analyze Tags**: Gather all existing tags from the YAML frontmatter of files in `docs/` to identify duplicates, typos, or inconsistent naming (e.g., `NT` vs `New Testament`).
4. **Check Metadata**: Verify that every file has a `title` and appropriate `tags` in its frontmatter.

### Phase 2: Navigation Cleanup

1. **Reorganize `mkdocs.yml`**: Propose or implement changes to the `nav` structure to improve user flow.
2. **Add Missing Pages**: Integrate orphan files into the navigation where appropriate.
3. **Synchronize Titles**: Ensure the labels in `nav` match the `title` defined in the file's frontmatter or its first H1 header.

### Phase 3: Tag & Metadata Standardization

1. **Consolidate Tags**: Rename inconsistent tags across the entire `docs/` folder (e.g., changing `life-of-elisha` and `elisha-series` to a single `Elisha` tag).
2. **Enforce Frontmatter Rules**:
    - Every file must have a YAML block at the very top.
    - Fields: `title`, `description` (optional), `tags`.
3. **Update `tags.md`**: If a dedicated tags page exists, ensure it is configured to display the current tag cloud.

### Phase 4: Asset & Link Validation

1. **Verify Images**: Ensure all `![alt text](path)` links use relative paths that resolve correctly within the `docs/` structure.
2. **Clean Up Assets**: Identify unused images in `docs/assets/`.
3. **Fix Redirects**: If files were moved, identify if any external links or high-traffic internal links need manual correction.

### Phase 5: Verification

1. **Dry Run Build**: Use `mkdocs build --strict` (if possible in the environment) to identify errors.
2. **Visual Check**: If a preview is available, verify that navigation menus and tag clouds render correctly.

---

## Key Guidelines

- **Surgical Edits**: When standardizing tags, use `replace` or `grep_search` to update multiple files efficiently.
- **Material Theme Features**: Leverage Material-specific features like `navigation.sections`, `navigation.indexes`, and admonitions.
- **Frontmatter Priority**: Prefer setting the page title in the YAML frontmatter `title` field rather than relying on MkDocs to infer it from the H1.
- **Relative Paths**: Always use relative paths for internal links (e.g., `[Link Text](other-file.md)` rather than `/other-file.md`).

---

## Standard Metadata Template

```yaml
---
title: "Page Title"
description: "Brief summary of the content for SEO and search results."
tags:
  - Category
  - Sub-Category
  - Topic
---
```
