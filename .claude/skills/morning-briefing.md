# Skill: Morning Briefing

A Claude Code skill that aggregates daily information and produces a structured briefing.

## Schedule (explicit)

- Intended cron schedule: **daily at 7:00 AM America/Toronto (ET)**
- Cron expression: `0 7 * * *`
- Timezone: `America/Toronto`

## Trigger

`/morning-briefing`

## Description

Produces a daily briefing saved to `briefings/YYYY-MM-DD.md`, covering research-relevant graphics/vision content and AI tooling news, and posts the same briefing to Slack `<#C0AJKTM85T5>`.

## Steps

1. Fetch today's events from Google Calendar (see Calendar section below)
2. Search for and select **3 articles on 3D graphics and vision** (see sources below)
3. Search for and select **5 articles on AI coding and efficiency tools** from Japanese-adjacent outlets
4. Check open GitHub Issues for due or overdue tasks
5. Write the briefing to `briefings/YYYY-MM-DD.md`
6. Post the briefing content to Slack `<#C0AJKTM85T5>`
7. Commit the file with message: `briefing: YYYY-MM-DD`

## Calendar

Use the Google Calendar MCP tool (or `gcalcli agenda` if available) to fetch today's events.
List all events in chronological order with time, title, and location/link if present.
If no MCP tool is available, note "Calendar unavailable" and skip the section.

## Sources

### 3D Graphics & Vision
Prioritize recent, substantive content. Include:
- ArXiv (cs.GR, cs.CV, cs.CG)
- SIGGRAPH / CVPR / ICCV / ECCV paper announcements
- Professor and researcher blogs (e.g., style of https://www.vincentsitzmann.com/blog/ — opinionated, research-grade commentary)
- Project pages for notable new work (NeRF, Gaussian splatting, geometry processing, rendering, reconstruction)
- Lab blogs (e.g., Google Research, Adobe Research, MIT CSAIL)

Selection criteria: prefer articles with novel ideas or strong opinions over press releases or summaries. Aim for the kind of thing a graphics PhD would forward to a labmate.

### AI Coding & Efficiency Tools
Sources (in rough priority order):
- Zenn (zenn.dev)
- Qiita (qiita.com)
- Hacker News (news.ycombinator.com)
- Reddit (r/LocalLLaMA, r/programming, r/MachineLearning)

Focus: tools, workflows, and techniques that improve developer productivity — editors, agents, CLI tools, prompt engineering for code, benchmarks.

## Output Format

```markdown
# Briefing: YYYY-MM-DD

## Today's Schedule

| Time | Event | Location / Link |
|------|-------|-----------------|
| 09:00 | ... | ... |

---

## 3D Graphics & Vision

1. **[Title](URL)**
   *Source · Author if known*
   One or two sentences on why it's worth reading.

2. ...

3. ...

---

## AI Coding & Efficiency Tools

1. **[Title](URL)**
   *Source*
   One or two sentences on the key takeaway.

2. ...

3. ...

4. ...

5. ...

---

## Open Tasks

- #issue-number: title (due: date or "no deadline")
```
