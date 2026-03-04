# Bootstrap

Setup guide and onboarding instructions for this workspace.

## Getting Started

This workspace uses GitHub as a personal life management hub, with Claude Code as the primary AI assistant.

## Prerequisites

- GitHub account with this repository
- Claude Code CLI installed
- GitHub CLI (`gh`) installed and authenticated

## Initial Setup

1. Clone this repository
2. Install Claude Code: `npm install -g @anthropic-ai/claude-code`
3. Authenticate GitHub CLI: `gh auth login`
4. Review and customize `SOUL.md`, `USER.md`, and `AGENTS.md`

## Skill Installation

Skills live in `.claude/skills/`. Each skill is a markdown file defining a Claude Code slash command.

```
.claude/skills/
├── morning-briefing.md    # Daily briefing aggregation
├── weekly-review.md       # Weekly reflection and planning
└── draft-article.md       # Article drafting workflow
```

## Task Management

Tasks are tracked as GitHub Issues with Projects v2 for deadline and status management.

- Create tasks: `gh issue create`
- View board: Open the GitHub Projects board in your browser

## Daily Workflow

<!-- Describe the intended daily routine using this system -->
