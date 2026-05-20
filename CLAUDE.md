# CLAUDE.md

## Task creation

When creating a task, it must be a `.md` file with the following frontmatter structure:

```markdown
---
kanbaruuType: "task"
kanbaruuTaskId: "task_<id>"
schemaVersion: 1
title: "Task title"
columnId: "col_<id>"
columnName: "Column name"
priority: "HIGH" # HIGH | MEDIUM | LOW
position: 0
startAt: "2026-05-05T09:00:00.000Z"
endAt: "2026-05-07T17:00:00.000Z"
tags:
  - "Tag1"
assigneeEmails:
  - "user@example.com"
goals:
  - id: "goal_<id>"
    text: "Goal description"
    completed: false
    position: 0
---

Task body / description goes here.
```

### Required fields

| Field | Type | Notes |
|---|---|---|
| `kanbaruuType` | string | Always `"task"` |
| `kanbaruuTaskId` | string | Unique ID, e.g. `task_homepage_copy_01` |
| `schemaVersion` | number | Always `1` |
| `title` | string | Human-readable task title |
| `columnId` | string | ID of the board column |
| `columnName` | string | Display name of the column |
| `priority` | string | `HIGH`, `MEDIUM`, or `LOW` |
| `position` | number | Sort order within the column |

### Optional fields

| Field | Type | Notes |
|---|---|---|
| `startAt` | ISO 8601 string | Task start date/time |
| `endAt` | ISO 8601 string | Task due date/time |
| `tags` | string[] | List of tag labels |
| `assigneeEmails` | string[] | Emails of assigned users |
| `goals` | object[] | Checklist items; each has `id`, `text`, `completed`, `position` |
