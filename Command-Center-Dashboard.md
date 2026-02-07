---
cssclasses:
  - dashboard
  - command-center
---

# 🎯 Command Center

### Last updated: `= dateformat(date(now), "MMM dd, yyyy hh:mm a")`

---

## 📊 Core Databases

### Projects DB
![[Projects-DB.base]]


### Areas DB
![[Areas-DB.base]]

### Resources DB
![[Resources-DB.base]]

### All Tasks DB
![[All-Tasks-DB.base]]

### Simple Notes DB
![[Simple-Notes-DB.base]]

---

## ⚡ Quick Capture

```button
name 💡 New Idea
type command
action Templater: Create new note from template
templater: true
template: Templates/Idea-Template.md
color: blue
```

```button
name 👥 New Friend
type command
action Templater: Create new note from template
templater: true
template: Templates/Friend-Template.md
color: green
```

```button
name ✍️ New Prompt
type command
action Templater: Create new note from template
templater: true
template: Templates/Prompt-Template.md
color: purple
```

---


## 🔍 Key Views

### Active Projects (Using Dataview as alternative)
```dataview
TABLE
  status as "Status",
  priority as "Priority",
  due-date as "Due Date",
  progress as "Progress"
FROM "Projects"
WHERE type = "project" AND (status = "In Progress" OR status = "Todo" OR status = "Planning")
SORT priority DESC, due-date ASC
```

### Upcoming Tasks
```dataview
TASK
WHERE !completed
AND due-date >= date(today)
AND due-date <= date(today) + dur(7 days)
SORT due-date ASC
```

### Recent Activity
```dataview
TABLE 
  file.ctime as "Created",
  file.mtime as "Modified",
  tags as "Tags"
FROM ""
WHERE file.mtime >= date(today) - dur(7 days)
SORT file.mtime DESC
LIMIT 10
```

---

## 🎨 Dashboard Navigation

[[Projects/Projects-MOC|📁 All Projects]] | [[Areas/Areas-MOC|🗂️ All Areas]] | [[Resources/Resources-MOC|📚 All Resources]] | [[Tasks/Tasks-MOC|✅ All Tasks]] | [[Daily Notes/Daily-Notes-MOC|📆 Daily Notes]]

---

## 📝 Notes

> Add your dashboard notes or quick thoughts here...

