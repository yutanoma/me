# Skill: Evening Briefing

A Claude Code skill for end-of-day wrap-up and next-day preparation.

## Schedule (explicit)

- Intended cron schedule: **daily at 7:00 PM America/Toronto (ET)**
- Cron expression: `0 19 * * *`
- Timezone: `America/Toronto`

## Trigger

`/evening-briefing`

## Description

Produces a short evening briefing saved to `briefings/YYYY-MM-DD-evening.md`, focused on wrapping up the current day and previewing tomorrow, and posts the same briefing to Slack `<#C0AJNSPTAJ1>`.

## Steps

1. Fetch tomorrow's events from Google Calendar (see Calendar section below)
2. Check open GitHub Issues — flag anything due tomorrow or overdue
3. Write the briefing to `briefings/YYYY-MM-DD-evening.md`
4. Post the briefing content to Slack `<#C0AJNSPTAJ1>`
5. Commit the file with message: `briefing: YYYY-MM-DD evening`

## Calendar

Use the Google Calendar MCP tool (or absolute-path `gcalcli` as fallback) to fetch tomorrow's events.

Preferred fallback command (force ET rendering):
- `TZ=America/New_York /usr/local/bin/gcalcli agenda` (avoid PATH issues in cron/non-login shells; always display in ET)
List all events in chronological order with time, title, and location/link if present.
If no MCP tool is available, note "Calendar unavailable" and skip the section.

## Output Format

```markdown
# Evening Briefing: YYYY-MM-DD

## Tomorrow's Schedule

| Time | Event | Location / Link |
|------|-------|-----------------|
| 09:00 | ... | ... |

---

## Tasks Due Tomorrow

- #issue-number: title

---

## Notes

<!-- Optional: anything to carry over or remember for tomorrow -->
```
