# Skill: Morning Briefing

A Claude Code skill that aggregates daily information and produces a structured briefing.

## Trigger

`/morning-briefing`

## Description

Pulls together tech news, task updates, calendar items, and personal notes into a single daily briefing saved to `briefings/YYYY-MM-DD.md`.

## Steps

1. Check open GitHub Issues for due or overdue tasks
2. Aggregate news from configured sources
3. Summarize any pending notes or drafts
4. Write the briefing file to `briefings/`
5. Commit the briefing to git

## Output Format

```markdown
# Briefing: YYYY-MM-DD

## Tasks
- [ ] ...

## News
- ...

## Notes
- ...
```

## Configuration

<!-- Add source URLs or filters here -->
