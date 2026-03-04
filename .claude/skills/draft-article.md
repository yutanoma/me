# Skill: Draft Article

A Claude Code skill for drafting long-form articles from notes or ideas.

## Trigger

`/draft-article`

## Description

Takes a topic or rough notes and produces a structured article draft saved to `notes/articles/`.

## Steps

1. Ask for the topic, target audience, and any existing notes
2. Generate an outline
3. Draft the full article
4. Save to `notes/articles/YYYY-MM-DD-slug.md`
5. Commit the draft to git

## Output Format

```markdown
---
title: ""
date: YYYY-MM-DD
status: draft
tags: []
---

# Title

## Introduction

## Section 1

## Section 2

## Conclusion
```
