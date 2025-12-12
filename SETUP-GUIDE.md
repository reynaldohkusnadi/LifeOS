# 🚀 Command Center Setup Guide

This guide will help you set up a Notion-like Command Center dashboard in Obsidian using the new **Bases** feature and other powerful plugins.

## 📋 Table of Contents
1. [Required Plugins](#required-plugins)
2. [Folder Structure](#folder-structure)
3. [Installation Steps](#installation-steps)
4. [Setting Up Bases](#setting-up-bases)
5. [Configuring Quick Capture](#configuring-quick-capture)
6. [Using the Dashboard](#using-the-dashboard)
7. [Advanced Features](#advanced-features)
8. [Troubleshooting](#troubleshooting)

---

## 1. Required Plugins

### Core Plugin (Built-in)
- **Bases** - Native database functionality (Enable in Settings → Core plugins)

### Community Plugins (Install from Community Plugins)
1. **Templater** - For dynamic templates and quick capture
2. **Buttons** - For creating clickable quick capture buttons
3. **Dataview** - For advanced queries (optional but recommended)
4. **Homepage** or **Dashboard++** - To set dashboard as home page
5. **Meta Bind** - For inline buttons and inputs (optional)

### Optional Enhancement Plugins
- **Calendar** - For daily notes integration
- **Tasks** - Enhanced task management
- **Kanban** - Kanban board views
- **Charts** - Data visualization

---

## 2. Folder Structure

Create the following folder structure in your vault:

```
Your Vault/
├── 📊 Command-Center-Dashboard.md (Main Dashboard)
├── Templates/
│   ├── Idea-Template.md
│   ├── Friend-Template.md
│   ├── Prompt-Template.md
│   ├── Project-Template.md
│   ├── Area-Template.md
│   ├── Task-Template.md
│   └── Resource-Template.md
├── Projects/
│   └── (Your project notes go here)
├── Areas/
│   └── (Your area notes go here)
├── Resources/
│   └── (Your resource notes go here)
├── Tasks/
│   └── (Your task notes go here)
├── Notes/
│   └── (Your general notes go here)
└── Bases/
    ├── Projects-DB.base
    ├── Areas-DB.base
    ├── Resources-DB.base
    ├── All-Tasks-DB.base
    └── Simple-Notes-DB.base
```

---

## 3. Installation Steps

### Step 1: Enable Bases (Core Plugin)
1. Go to **Settings** → **Core plugins**
2. Find **Bases** and toggle it ON
3. Restart Obsidian if needed

### Step 2: Install Community Plugins
1. Go to **Settings** → **Community plugins**
2. Click **Browse** 
3. Search for each plugin and click **Install**, then **Enable**:
   - Templater
   - Buttons
   - Dataview (optional)
   - Homepage or Dashboard++ (optional)

### Step 3: Configure Templater
1. Go to **Settings** → **Templater**
2. Set **Template folder location** to `Templates`
3. Enable **Trigger Templater on new file creation**
4. Configure hotkeys if desired

### Step 4: Configure Buttons
1. Go to **Settings** → **Buttons**
2. Review button styles and adjust to your preference
3. No additional configuration needed for basic use

---

## 4. Setting Up Bases

### Understanding Bases

Bases are Obsidian's native database feature. They work by:
- Reading YAML frontmatter (properties) from your notes
- Displaying notes in table or card views
- Allowing you to filter, sort, and create formulas
- Storing view configurations in `.base` files

### Creating Your First Base

#### Method 1: Using Provided .base Files
1. Copy all `.base` files to a `Bases/` folder in your vault
2. Open any `.base` file to see the database view
3. Customize filters, columns, and sorts as needed

#### Method 2: Creating Manually
1. Right-click on a folder (e.g., `Projects`)
2. Select **New base**
3. Configure:
   - **Source:** Select folder to pull notes from
   - **Columns:** Add properties you want to display
   - **Filters:** Set conditions for which notes to show
   - **Sort:** Define how notes should be ordered

### Configuring Each Database

#### Projects DB
**Key Properties:**
- `status` (text): Todo, In Progress, Done, Archived
- `priority` (text): High, Medium, Low
- `area` (link): Link to related Area note
- `due-date` (date): Project deadline
- `progress` (number): 0-100%
- `related-tasks` (list): Links to task notes

#### Areas DB
**Key Properties:**
- `type` (text): Personal, Work, Learning, Health, etc.
- `projects` (list): Links to related projects
- `last-reviewed` (date): When area was last reviewed
- `goals` (list): Goals for this area

#### Resources DB
**Key Properties:**
- `category` (text): Article, Book, Video, Course, Tool
- `type` (text): Sub-type classification
- `rating` (number): 0-5 stars
- `url` (text): Link to resource
- `date-added` (date): When added

#### Tasks DB
**Key Properties:**
- `task-name` (text): Task title
- `project` (link): Link to parent project
- `status` (text): Todo, In Progress, Done
- `priority` (text): High, Medium, Low
- `due-date` (date): Task deadline
- `area` (link): Link to related area

**Important:** The `project-status` column uses a formula:
```
this.project.status
```
This is a **rollup** that pulls the status from the linked project note.

### Embedding Bases in Dashboard

In your dashboard, embed bases using:

```markdown
![[Projects-DB]]
```

Or use the base query syntax:
```base
name: Projects View
source: Projects
columns: [...]
```

---

## 5. Configuring Quick Capture

### Setting Up Buttons

The buttons in your dashboard use the Buttons plugin syntax:

```markdown
\```button
name 💡 New Idea
type command
action Templater: Create new note from template
templater: true
template: Templates/Idea-Template.md
color: blue
\```
```

### Customizing Templates

Edit the template files in your `Templates/` folder:
- Add or remove properties in the YAML frontmatter
- Customize the content structure
- Use Templater syntax for dynamic content:
  - `<% tp.date.now("YYYY-MM-DD") %>` - Current date
  - `<% tp.file.title %>` - File name
  - `<% tp.date.now("YYYY-MM-DD", 7) %>` - Date 7 days from now

### Hotkeys for Quick Capture

Set up hotkeys in **Settings** → **Hotkeys**:
- Search for "Templater: Create new note from template"
- Assign hotkeys like `Ctrl+Shift+I` for ideas, etc.

---

## 6. Using the Dashboard

### Daily Workflow

1. **Morning:**
   - Open Command Center dashboard
   - Review active projects in Projects DB
   - Check tasks due today in All Tasks DB
   - Set daily priority in Make Time section

2. **During Day:**
   - Use Quick Capture for new ideas, contacts, or prompts
   - Update task statuses in Tasks DB
   - Add new resources as you discover them

3. **Evening:**
   - Update project progress
   - Log daily gratitude in Make Time
   - Review completed tasks

### Weekly Review

Use the Make Time section for weekly planning:
- Set priorities for each day
- Log gratitude daily
- Switch between Week/Clean/All views

### Database Management

**Filtering:**
- Click column headers to sort
- Use filter options in Bases settings
- Create saved views for common filters

**Editing:**
- Click any cell to edit inline
- Changes save automatically to note files
- Properties update in YAML frontmatter

**Relations:**
- Link projects to areas using `area: "[[Area Name]]"`
- Link tasks to projects using `project: "[[Project Name]]"`
- Use rollups to display related data

---

## 7. Advanced Features

### Creating Formulas in Bases

Bases support formulas for dynamic calculations:

**Example: Count Projects in an Area**
```
length(this.projects)
```

**Example: Days Until Due**
```
this.due-date - date(today)
```

**Example: Rollup Project Status**
```
this.project.status
```

### Using Dataview for Custom Views

While Bases handle most needs, Dataview offers more flexibility:

```dataview
TABLE 
  status as "Status",
  priority as "Priority",
  due-date as "Due"
FROM "Projects"
WHERE status = "In Progress"
SORT priority DESC, due-date ASC
```

### Card View for Visual Management

Switch any Base to card view:
1. Open the Base
2. Click view options
3. Select **Card view**
4. Configure card layout and cover images

### Automating with Templater

Create dynamic templates:

```markdown
---
created: <% tp.date.now("YYYY-MM-DD") %>
weekly-goal: <% tp.system.prompt("What's your goal this week?") %>
---
```

---

## 8. Troubleshooting

### Common Issues

#### Bases Not Showing Data
**Problem:** Base appears empty even though notes exist

**Solutions:**
- Ensure notes have proper YAML frontmatter/properties
- Check that source folder path is correct in `.base` file
- Verify properties are spelled correctly (case-sensitive)
- Try reloading Obsidian

#### Templates Not Working
**Problem:** Templater syntax not rendering

**Solutions:**
- Verify Templater plugin is enabled
- Check template folder path in settings
- Ensure template files have correct syntax
- Test with a simple template first

#### Buttons Not Appearing
**Problem:** Button code shows as text

**Solutions:**
- Ensure Buttons plugin is enabled
- Check that you're in Reading view (not Editing mode)
- Verify button syntax is correct (no escape characters)
- Restart Obsidian

#### Relations Not Working
**Problem:** Rollups show empty or undefined

**Solutions:**
- Ensure linked notes exist
- Use proper link format: `[[Note Name]]`
- Check that linked notes have the required property
- Verify formula syntax in Base settings

#### Properties Not Syncing
**Problem:** Changes in Base don't update note files

**Solutions:**
- Wait a few seconds (sometimes delayed)
- Check that property names match exactly
- Ensure note isn't open in another pane
- Try editing directly in note to verify

### Performance Tips

**For Large Vaults:**
- Limit Base queries with filters
- Use recursive: false when possible
- Set reasonable limits on number of results
- Close unused Bases when not needed

**For Slow Rendering:**
- Reduce number of columns displayed
- Remove complex formulas
- Disable card view images if not needed
- Clear cache: Settings → About → Reload without cache

---

## 🎯 Next Steps

1. **Customize Properties:** Add properties specific to your workflow
2. **Create More Templates:** Build templates for your common note types
3. **Set Up Weekly Review:** Use dashboard for regular reviews
4. **Explore Card Views:** Visualize projects as kanban boards
5. **Integrate Daily Notes:** Link dashboard to your daily notes
6. **Add Custom CSS:** Style your dashboard with custom CSS snippets

---

## 📚 Additional Resources

### Official Documentation
- [Obsidian Bases Documentation](https://help.obsidian.md/bases)
- [Templater Documentation](https://silentvoid13.github.io/Templater/)
- [Dataview Documentation](https://blacksmithgu.github.io/obsidian-dataview/)

### Community Resources
- Obsidian Forum: https://forum.obsidian.md/
- Obsidian Discord: https://discord.gg/obsidianmd
- r/ObsidianMD: https://reddit.com/r/ObsidianMD

---

## ✅ Quick Start Checklist

- [ ] Install required plugins
- [ ] Create folder structure
- [ ] Copy template files to Templates folder
- [ ] Copy .base files to Bases folder
- [ ] Enable Bases core plugin
- [ ] Configure Templater settings
- [ ] Test Quick Capture buttons
- [ ] Create your first project note
- [ ] Verify Bases are displaying correctly
- [ ] Set dashboard as homepage (optional)
- [ ] Customize to your workflow

---

**Congratulations!** You now have a powerful Command Center dashboard in Obsidian. Start capturing projects, tasks, and ideas, and watch your productivity soar! 🚀
