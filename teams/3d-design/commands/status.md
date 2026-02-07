---
description: Show 3d-design team status and recent activity
argument-hint: [verbose]
---

# 3D Design Team Status

Show the current status and recent activity of the 3d-design team.

## Usage

```
/3d-design:status
/3d-design:status verbose
```

## Actions

1. Read the team configuration from `teams/3d-design/team.json`
2. Display team information:
   - Team name and description
   - Team version
   - Team members with roles, phases, and colors
   - Available workflows
3. Check the team log file at `~/.claude/team-logs/3d-design.jsonl` if it exists
4. Display recent activity:
   - Recent tool usage
   - Files modified
   - Timestamps
5. If `verbose` is specified, show more detailed information

## Output Format

```
# 3D Design Team Status

## Team Information
- **Team**: 3d-design
- **Version**: 1.0.0
- **Description**: 3D design team for modeling, animation, rigging, texturing, VTuber creation, and asset optimization

## Team Members

| Agent | Role | Phase | Color |
|-------|------|-------|-------|
| 3d-3d-analyst | 3D Analyst | discovery | yellow |
| 3d-modeler | 3D Modeler | execution | green |
| 3d-rigger | 3D Rigger | execution | cyan |
| 3d-animator | 3D Animator | execution | magenta |
| 3d-texturer | 3D Texturer | execution | blue |
| 3d-vtuber-specialist | VTuber Specialist | execution | orange |
| 3d-asset-optimizer | Asset Optimizer | review | red |

## Available Workflows

- **asset**: Asset creation and production (5 phases)
- **character**: Character creation pipeline (5 phases)
- **scene**: Scene creation pipeline (5 phases)
- **vtuber**: VTuber avatar creation (5 phases)
- **optimization**: Asset optimization (3 phases)

## Recent Activity

[Recent tool usage and file modifications]

## Telemetry

Tool usage is logged to `~/.claude/team-logs/3d-design.jsonl`
```
