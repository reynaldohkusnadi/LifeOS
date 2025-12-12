---
type: area
area-type: Health
projects: []
last-reviewed: 2025-11-23
review-frequency: Monthly
goals:
  - Being Indonesian Carlos Alcaraz 
tags:
  - area
  - domain
created: 2025-11-23
modified: 2025-11-23
---

# 🗂️ Tennis

## Area Description

Handles all of my Tennis related project with the ultimate goal of being Indonesian Carlos Alcaraz 



## Current Goals
- Maintain 80 Kg
- Join an ameture tennis competition 
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
| Metric      | Current | Target     | Status   |
| ----------- | ------- | ---------- | -------- |
| Body Weight | 80      | 79 - 81 kg | on track |
| Metric 2    | -       | -          | -        |

## Quick Links & Resources
<!-- Additional notes and reference links -->
-

## Review History

### 2025-11-23 Review
**Status:** 
**What's working:** 
**What needs attention:** 
**Actions:**
- [ ] 
- [ ] 

## Notes


---
*Area created: 2025-11-23 23:27*
