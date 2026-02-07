---
type: project
status: Planning
priority: High
area: "[[Area Name]]"
due-date: <% tp.date.now("YYYY-MM-DD", 30) %>
progress: 0
start-date: <% tp.date.now("YYYY-MM-DD") %>
related-tasks: []
tags:
  - project
created: <% tp.date.now("YYYY-MM-DD") %>
modified: <% tp.date.now("YYYY-MM-DD") %>
---

# 📁 <% tp.file.title %>

## Project Overview
<!-- Brief description of what this project aims to achieve -->


## Objectives
- [ ] Objective 1
- [ ] Objective 2
- [ ] Objective 3

## Key Milestones
| Milestone | Target Date | Status |
|-----------|-------------|--------|
| Milestone 1 | YYYY-MM-DD | 🟡 In Progress |
| Milestone 2 | YYYY-MM-DD | ⚪ Not Started |
| Milestone 3 | YYYY-MM-DD | ⚪ Not Started |

## Tasks

```base
filters:
  and:
    - file.inFolder(this.file.folder)
    - 'type == "task"'
properties:
  task-name:
    displayName: Task
  status:
    displayName: Status
  priority:
    displayName: Priority
  due-date:
    displayName: Due Date
views:
  - type: table
    name: Project Tasks
    order:
      - file.name
      - task-name
      - status
      - priority
      - due-date
```

## Resources & Links
- 
- 

## Stakeholders
- 
- 

## Notes & Updates

### <% tp.date.now("YYYY-MM-DD") %>
<!-- Project updates and notes go here -->


## Project Status
**Current Status:** Planning
**Progress:** 0%
**Next Steps:**
1. 
2. 
3. 

---
*Project created: <% tp.date.now("YYYY-MM-DD HH:mm") %>*
