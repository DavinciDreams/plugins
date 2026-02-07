---
description: Show mobile-dev team status and recent activity
argument-hint: [verbose]
---

# Mobile Dev Team Status

Display the current status of the mobile-dev team and recent activity.

## Actions

1. Read the team configuration from `team.json`
2. Check the team log file at `~/.claude/team-logs/mobile-dev.jsonl`
3. Display team roster with all agents
4. If verbose, show recent tool usage from the log
5. Display team version and description

## Output Format

```
Mobile Dev Team (v1.0.0)
Mobile development team for iOS, Android, and cross-platform applications

Team Roster:
- mobile-mobile-analyst (yellow) - Mobile Requirements Analyst [discovery]
- mobile-ios-developer (green) - iOS Developer [execution]
- mobile-android-developer (cyan) - Android Developer [execution]
- mobile-cross-platform-dev (magenta) - Cross-Platform Developer [execution]
- mobile-mobile-qa (red) - Mobile QA Engineer [review]

[Verbose output shows recent tool usage]
```
