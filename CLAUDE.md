# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is an **Obsidian vault** implementing a Notion-style Command Center dashboard using Obsidian's native **Bases** feature. It provides a local-first, markdown-based personal productivity system with relational databases.

**Not a traditional codebase:** This repository contains markdown files, templates, and configuration files for Obsidian, not executable code. All "development" involves editing markdown templates, YAML configurations, and CSS styling.

## Core Architecture

### PARA Method Structure
The vault follows the PARA organizational method:
- **Projects/** - Active projects with defined goals and timelines
- **Areas/** - Ongoing areas of responsibility
- **Resources/** - Reference materials (articles, books, tools)
- **Tasks/** - Individual tasks linked to projects
- **Notes/** - General notes and quick captures

### Obsidian Bases System
Bases are Obsidian's native database feature (similar to Notion databases):
- **`.base` files** in `Bases/` folder define database views
- Read YAML frontmatter properties from markdown files in source folders
- Support filtering, sorting, formulas, and rollup properties
- Display data in table or card views

### Key Components
1. **[Command-Center-Dashboard.md](Command-Center-Dashboard.md)** - Main dashboard with embedded database views and quick capture buttons
2. **Templates/** - Templater templates for creating new notes with pre-filled YAML properties
3. **Bases/** - Database view configurations (`.base` files)
4. **.obsidian/snippets/command-center.css** - Custom styling for dashboard UI

## Important File Formats

### Base Files (.base)
YAML configuration files that define database views:

```yaml
name: Database Name
source:
  type: folder
  path: FolderName
  recursive: true
columns:
  - type: property
    key: property-name
    label: Display Name
    width: 150
  - type: formula
    key: computed-field
    formula: this.linkedProperty.field  # Rollup example
sort:
  - by: property-name
    order: desc
filters:
  - type: property
    property: status
    operator: is
    value: Active
view: table  # or "card"
```

### Template Files
Markdown files using **Templater syntax** (not standard template literals):
- `2025-12-10` - Current date
- `2025-12-17` - Date 7 days from now
- `CLAUDE` - Current file title
- `null` - Interactive prompt

### YAML Frontmatter Properties
All notes use YAML frontmatter for database fields:

**Common Properties:**
- `status`: Text values like "Todo", "In Progress", "Done", "Archived"
- `priority`: "High", "Medium", "Low"
- `type`: Note type classification
- `tags`: List of tags
- `created`: ISO date (YYYY-MM-DD)
- `modified`: ISO date
- Links to other notes: `property-name: "[[Note Name]]"`
- Lists of links: `property-name: ["[[Note 1]]", "[[Note 2]]"]`

**Important:** Property names must match exactly (case-sensitive) between templates, base files, and note frontmatter.

## Relational Database Features

### Link Relationships
**One-to-Many (Single Link):**
```yaml
project: "[[My Project]]"
```

**Many-to-Many (List of Links):**
```yaml
projects:
  - "[[Project A]]"
  - "[[Project B]]"
```

### Rollup Formulas
Display properties from linked notes using dot notation in Base formulas:

```yaml
# In All-Tasks-DB.base
- type: formula
  key: project-status
  formula: this.project.status  # Shows status from linked project
```

**Formula Examples:**
- `this.project.status` - Get status from linked project
- `length(this.projects)` - Count number of linked projects
- `this.area.type` - Get type from linked area

## Modifying the System

### Adding a New Template
1. Create markdown file in `Templates/` folder
2. Add YAML frontmatter with desired properties
3. Use Templater syntax for dynamic content
4. Reference from dashboard buttons or use Templater command

### Creating a New Database View
1. Create `.base` file in `Bases/` folder
2. Define source folder and columns
3. Add filters and sorting as needed
4. Embed in dashboard using: `![[ViewName-DB]]` or inline base query

### Modifying Existing Templates
When editing templates in `Templates/`:
- Preserve YAML frontmatter structure
- Keep property names consistent with Base configurations
- Use Templater syntax, not JavaScript template literals
- Test with Templater's "Create new note from template" command

### Updating Dashboard
[Command-Center-Dashboard.md](Command-Center-Dashboard.md) structure:
- **Base queries** (inline `\`\`\`base` blocks) - Embedded database views
- **Buttons** (`\`\`\`button` blocks) - Quick capture with Templater integration
- **Dataview queries** (optional alternative to Bases)
- **Make Time section** - Weekly planning with daily priorities

### Styling Changes
Edit [.obsidian/snippets/command-center.css](.obsidian/snippets/command-center.css):
- Must be enabled in Obsidian Settings → Appearance → CSS snippets
- Changes apply after toggling snippet off/on or reloading Obsidian

## Required Plugins

**Core Plugin (built-in):**
- **Bases** - Must be enabled in Settings → Core plugins

**Community Plugins (already installed):**
- **Templater** - Dynamic templates (folder set to `Templates/`)
- **Buttons** - Quick capture buttons in dashboard
- **Dataview** - Advanced queries (optional, Bases is primary)
- **Homepage** - Set Command Center as default page
- **Make.md** - Enhanced navigation and folder management

## Common Workflows

### Creating a New Project
1. Use Project-Template.md (via Templater or button)
2. Fill in YAML properties: status, priority, area, due-date
3. Link to an existing Area note: `area: "[[Area Name]]"`
4. Project automatically appears in Projects-DB

### Creating Tasks for a Project
1. Use Task-Template.md
2. Link to project: `project: "[[Project Name]]"`
3. Task appears in All-Tasks-DB with project status rollup

### Adding Relational Properties
To create new relationships between note types:
1. Add link property to template YAML
2. Add corresponding column in Base file
3. Optionally create rollup formula to display linked data

### Troubleshooting Base Views
If a Base shows empty or missing data:
- Verify source folder path matches actual folder name
- Check that notes have required properties in frontmatter
- Ensure property names match exactly (case-sensitive)
- Confirm YAML syntax is valid (proper indentation, quotes)

## Second Brain: AI-Powered Resource Capture

The vault includes a "Second Brain" feature that uses Claude to capture, summarize, and organize online content automatically.

### How It Works
1. User provides a URL or file path to Claude Code
2. Claude fetches content (transcript, article text, PDF content)
3. Claude summarizes and extracts key takeaways
4. Claude categorizes content and generates relevant tags
5. Claude creates a properly formatted resource note in `Resources/`

### Supported Content Types
| Type | Source | How It's Processed |
|------|--------|-------------------|
| YouTube Videos | `youtube.com`, `youtu.be` | Transcript extracted via MCP, summarized |
| Web Articles | Any URL | Page fetched, content extracted and summarized |
| PDFs | Local file path | Read directly, content summarized |
| Twitter/X | `twitter.com`, `x.com` | Thread content fetched and summarized |

### Using the Capture Command
Run `/capture-resource` or ask Claude to "capture this: [URL]"

Example:
```
User: Capture this: https://youtube.com/watch?v=xyz

Claude will:
1. Detect content type (YouTube video)
2. Fetch transcript
3. Generate summary and key takeaways
4. Determine Area (e.g., [[AI]])
5. Generate tags for graph linking
6. Write note to Resources/Video Title.md
```

### Tag Structure for Auto-Linking
Tags enable automatic connections in Obsidian's graph view:

| Tag Type | Purpose | Examples |
|----------|---------|----------|
| Domain | Links to Areas | `ai`, `finance`, `learning`, `business` |
| Topic | Specific concepts | `machine-learning`, `investing`, `productivity` |
| Format | Content type | `video`, `article`, `tutorial` |
| Source | Platform | `youtube`, `twitter`, `substack` |

### Area Detection
Claude automatically maps content to existing Areas:
- **AI content** → `[[AI]]`
- **Finance/investing** → `[[Finance]]`
- **Learning/education** → `[[Learning]]`
- **Business/startups** → `[[Big Beautiful Business Idea]]`
- **Tennis** → `[[Tennis]]`
- **Fitness/health** → `[[Gym]]`

### Claude Skill Location
The capture logic is defined in: `.claude/commands/capture-resource.md`

## File Naming Conventions

- **Templates:** `Type-Template.md` (e.g., Project-Template.md)
- **Bases:** `Type-DB.base` (e.g., Projects-DB.base)
- **Notes:** Use descriptive names; Templater will prompt for title
- **Folders:** Single word or hyphenated (Projects, Areas, Resources, Tasks, Notes)

## Important Notes

- **This is not a code project** - No compilation, building, or testing commands
- **All data is in markdown files** - Every note is a standalone .md file
- **Bases read from folders** - Database views are dynamic queries over folder contents
- **Templater is not JavaScript** - Use Templater syntax, not ES6 template literals
- **Properties are case-sensitive** - `Status` ≠ `status`
- **Links must use wiki-link format** - `[[Note Name]]` not `[Note Name](path)`
- **Formulas use dot notation** - `this.property.subproperty` for rollups

## Reference Documentation

See these files for detailed information:
- [README.md](README.md) - Project overview and features
- [SETUP-GUIDE.md](SETUP-GUIDE.md) - Installation and configuration guide
- [FILE-MANIFEST.md](FILE-MANIFEST.md) - Complete file listing
- [Command-Center-Dashboard.md](Command-Center-Dashboard.md) - Live dashboard example