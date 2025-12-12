# 📦 File Manifest & Installation Guide

## 📁 Package Contents

This package contains everything you need to set up a Command Center dashboard in Obsidian. Below is a complete list of files and their purposes.

---

## 🗂️ Core Files

### 📊 Command-Center-Dashboard.md
**Location:** Root of your vault  
**Purpose:** Main dashboard file - your command center  
**Usage:** Open this as your daily hub

### 📖 README.md
**Location:** Root (optional, for reference)  
**Purpose:** Overview and quick reference  
**Usage:** Read for understanding the system

### 🔧 SETUP-GUIDE.md
**Location:** Root (optional, for reference)  
**Purpose:** Detailed installation instructions  
**Usage:** Follow step-by-step for setup

---

## 🎨 Styling

### command-center.css
**Location:** `.obsidian/snippets/command-center.css`  
**Purpose:** Custom CSS for dashboard styling  
**Usage:**
1. Copy to `.obsidian/snippets/` folder in your vault
2. Go to Settings → Appearance → CSS snippets
3. Toggle "command-center" ON

---

## 📊 Base Files (.base)

These files configure your database views. Copy all to a `Bases/` folder.

### Projects-DB.base
**Creates:** Projects database view  
**Shows:** All projects with status, priority, area, due dates

### Areas-DB.base
**Creates:** Areas database view  
**Shows:** All areas of responsibility with project counts

### Resources-DB.base
**Creates:** Resources database view  
**Shows:** All resources with categories, ratings, URLs

### All-Tasks-DB.base
**Creates:** Tasks database view  
**Shows:** All tasks with project rollup (shows parent project status)

### Simple-Notes-DB.base
**Creates:** Notes database view  
**Shows:** Recent notes with timestamps

---

## 📝 Template Files (.md)

Copy all templates to a `Templates/` folder in your vault.

### Project-Template.md
**Purpose:** Create new project notes  
**Properties:** status, priority, area, due-date, progress  
**Usage:** Use for tracking projects

### Area-Template.md
**Purpose:** Create new area notes  
**Properties:** type, projects, last-reviewed, goals  
**Usage:** Define areas of responsibility

### Task-Template.md
**Purpose:** Create new task notes  
**Properties:** task-name, project, status, priority, due-date  
**Usage:** Track individual tasks

### Resource-Template.md
**Purpose:** Create new resource notes  
**Properties:** category, type, rating, url, date-added  
**Usage:** Save articles, books, videos, tools

### Idea-Template.md
**Purpose:** Quick capture for ideas  
**Properties:** type, status, tags, created  
**Usage:** Capture brainstorms and insights

### Friend-Template.md
**Purpose:** Quick capture for contacts  
**Properties:** type, category, birthday, location  
**Usage:** Track people and relationships

### Prompt-Template.md
**Purpose:** Quick capture for AI prompts  
**Properties:** type, category, model, effectiveness  
**Usage:** Build prompt library

---

## 📂 Required Folder Structure

Create these folders in your vault:

```
Your-Vault/
├── Templates/          ← Put all template files here
│   ├── Project-Template.md
│   ├── Area-Template.md
│   ├── Task-Template.md
│   ├── Resource-Template.md
│   ├── Idea-Template.md
│   ├── Friend-Template.md
│   └── Prompt-Template.md
├── Bases/              ← Put all .base files here
│   ├── Projects-DB.base
│   ├── Areas-DB.base
│   ├── Resources-DB.base
│   ├── All-Tasks-DB.base
│   └── Simple-Notes-DB.base
├── Projects/           ← Create: Your project notes
├── Areas/              ← Create: Your area notes
├── Resources/          ← Create: Your resource notes
├── Tasks/              ← Create: Your task notes
├── Notes/              ← Create: Your general notes
├── Command-Center-Dashboard.md
├── README.md (optional)
└── .obsidian/
    └── snippets/
        └── command-center.css
```

---

## 🔧 Required Plugins

Install these plugins from Obsidian's Community Plugins:

### Essential
1. **Bases** (Core Plugin - Built-in)
   - Enable in: Settings → Core plugins → Bases
   - Version: 1.9.0+

2. **Templater**
   - Install from: Community plugins
   - Configure: Set template folder to `Templates`

3. **Buttons**
   - Install from: Community plugins
   - No configuration needed

### Optional
4. **Dataview**
   - Install from: Community plugins
   - For advanced queries

5. **Homepage** or **Dashboard++**
   - Install from: Community plugins
   - Set Command Center as homepage

---

## ⚡ Quick Installation Steps

### Step 1: Prepare Vault
```
1. Create folders: Projects, Areas, Resources, Tasks, Notes
2. Create folder: Templates
3. Create folder: Bases
4. Create folder: .obsidian/snippets (if doesn't exist)
```

### Step 2: Copy Files
```
1. Copy all *-Template.md → Templates/
2. Copy all *.base → Bases/
3. Copy command-center.css → .obsidian/snippets/
4. Copy Command-Center-Dashboard.md → vault root
```

### Step 3: Install Plugins
```
1. Settings → Core plugins → Enable "Bases"
2. Settings → Community plugins → Browse
3. Install: Templater, Buttons, Dataview (optional)
4. Enable all installed plugins
```

### Step 4: Configure Templater
```
1. Settings → Templater
2. Set "Template folder location" to: Templates
3. Enable "Trigger Templater on new file creation"
```

### Step 5: Enable CSS
```
1. Settings → Appearance → CSS snippets
2. Click refresh icon
3. Toggle ON: command-center
```

### Step 6: Test
```
1. Open Command-Center-Dashboard.md
2. Try clicking "New Idea" button
3. Create a test project using Project-Template
4. Verify it appears in Projects-DB
```

---

## 🎯 First Time Usage

### Creating Your First Project
1. Use Project-Template.md to create a new project
2. Fill in properties: status, priority, area, due-date
3. Open Projects-DB.base to see it listed

### Creating Your First Task
1. Use Task-Template.md to create a new task
2. Link it to your project: `project: "[[Project Name]]"`
3. Open All-Tasks-DB.base to see project status rollup

### Understanding Relationships

**One-to-Many:**
```yaml
# In a Task
project: "[[My Project]]"  ← Links to one project
```

**Many-to-Many:**
```yaml
# In an Area
projects:
  - "[[Project A]]"
  - "[[Project B]]"
```

**Rollups (Automatic):**
```yaml
# In Tasks DB base file
project-status: this.project.status  ← Shows parent project's status
```

---

## 🎨 Customization Tips

### Change Database Columns
Edit `.base` files to add/remove columns:
```yaml
columns:
  - type: property
    key: your-custom-property
    label: Custom Label
    width: 150
```

### Add Custom Properties
Edit template files to add new properties:
```yaml
---
existing-property: value
my-new-field: custom value
---
```

### Modify Dashboard Layout
Edit `Command-Center-Dashboard.md`:
- Rearrange sections
- Add/remove databases
- Customize Make Time section

### Change Color Theme
Edit `command-center.css`:
- Modify color variables
- Adjust spacing
- Customize button styles

---

## ❓ FAQ

**Q: Do I need all these files?**  
A: Core files needed: Dashboard, Templates, Base files. CSS is optional but recommended.

**Q: Can I use this without Bases plugin?**  
A: No, Bases is essential. It's a core plugin (built-in), just needs to be enabled.

**Q: What if I already have templates?**  
A: You can integrate these into your existing system or use both.

**Q: Can I rename the folders?**  
A: Yes, but update paths in `.base` files accordingly.

**Q: How do I backup my data?**  
A: All data is in markdown files. Backup your vault folder regularly.

**Q: Will this work on mobile?**  
A: Bases work on mobile, but some plugins may have limitations.

---

## 🆘 Troubleshooting

### Bases showing empty
- **Check:** Properties exist in source notes
- **Check:** Folder paths in `.base` files
- **Check:** YAML syntax in frontmatter

### Buttons not working
- **Check:** Buttons plugin is enabled
- **Check:** You're in Reading view (not Edit)
- **Check:** Template paths are correct

### Templates not applying
- **Check:** Templater plugin enabled
- **Check:** Template folder set correctly
- **Check:** Templater syntax is valid

### CSS not applying
- **Check:** File in correct location
- **Check:** Snippet enabled in settings
- **Check:** Refresh CSS snippets

---

## 📚 Additional Resources

- **Obsidian Bases Docs:** https://help.obsidian.md/bases
- **Templater Docs:** https://silentvoid13.github.io/Templater/
- **Obsidian Forum:** https://forum.obsidian.md/
- **Obsidian Discord:** https://discord.gg/obsidianmd

---

## ✅ Installation Checklist

- [ ] Created all required folders
- [ ] Copied all template files to Templates/
- [ ] Copied all .base files to Bases/
- [ ] Copied CSS file to .obsidian/snippets/
- [ ] Copied dashboard to vault root
- [ ] Enabled Bases core plugin
- [ ] Installed Templater plugin
- [ ] Installed Buttons plugin
- [ ] Configured Templater settings
- [ ] Enabled CSS snippet
- [ ] Created test project
- [ ] Verified databases display correctly
- [ ] Tested quick capture buttons

---

**Need help?** Refer to SETUP-GUIDE.md for detailed instructions!

**Ready to start?** Open Command-Center-Dashboard.md and begin organizing! 🚀
