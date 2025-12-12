---
type: area
area-type: Personal
projects: []
last-reviewed: <% tp.date.now("YYYY-MM-DD") %>
review-frequency: Monthly
goals: []
tags:
  - area
  - domain
created: <% tp.date.now("YYYY-MM-DD") %>
modified: <% tp.date.now("YYYY-MM-DD") %>
---

# 🗂️ <% tp.file.title %>

## Area Description
<!-- What is this area of responsibility about? -->


## Current Goals
- 
- 
- 

## 📊 Area Dashboard

### 📁 Active Projects

```base
filters: file.inFolder("Projects") && area == this.file
properties:
  status:
    displayName: Status
  priority:
    displayName: Priority
  due-date:
    displayName: Due Date
  progress:
    displayName: Progress
views:
  - type: table
    name: Area Projects
    order:
      - file.name
      - status
      - priority
      - due-date
      - progress
    sort:
      - by: priority
        order: desc
      - by: due-date
        order: asc
```

### ✅ Area Tasks

```base
filters: file.inFolder("Tasks") && area == this.file
properties:
  status:
    displayName: Status
  priority:
    displayName: Priority
  due-date:
    displayName: Due
  project:
    displayName: Project
views:
  - type: table
    name: Area Tasks
    order:
      - file.name
      - status
      - priority
      - due-date
      - project
    sort:
      - by: status
        order: asc
      - by: priority
        order: desc
```

### 📚 Area Resources

```base
filters: file.inFolder("Resources") && area == this.file
properties:
  category:
    displayName: Category
  type:
    displayName: Type
  rating:
    displayName: Rating
  date-added:
    displayName: Added
views:
  - type: table
    name: Area Resources
    order:
      - file.name
      - category
      - type
      - rating
      - date-added
    sort:
      - by: rating
        order: desc
      - by: date-added
        order: desc
```

## Standards & Guidelines
<!-- What standards do you maintain in this area? -->


## Key Metrics
| Metric | Current | Target | Status |
|--------|---------|--------|--------|
| Metric 1 | - | - | - |
| Metric 2 | - | - | - |

## Quick Links & Resources
<!-- Additional notes and reference links -->
-

## Review History

### <% tp.date.now("YYYY-MM-DD") %> Review
**Status:** 
**What's working:** 
**What needs attention:** 
**Actions:**
- [ ] 
- [ ] 

## Notes


---
*Area created: <% tp.date.now("YYYY-MM-DD HH:mm") %>*
