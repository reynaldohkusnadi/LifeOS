# 🎯 Obsidian Command Center Dashboard

A complete Notion-style Command Center dashboard for Obsidian using the new **Bases** feature (released May 2025). This system replicates Notion's relational database functionality with local markdown files.

![Dashboard Preview](https://img.shields.io/badge/Obsidian-1.9.0+-purple?logo=obsidian)
![License](https://img.shields.io/badge/License-MIT-blue)

## ✨ Features

- **📊 Relational Databases** - Projects, Areas, Resources, Tasks, and Notes databases with relationships
- **🔄 Rollup Properties** - Display related data (e.g., show project status in task views)
- **⚡ Quick Capture** - One-click buttons for ideas, contacts, and prompts
- **📅 Weekly Planning** - Make Time section for priorities and gratitude
- **🎨 Beautiful UI** - Clean, Notion-inspired interface
- **🔍 Smart Filters** - Dynamic views with sorting and filtering
- **📝 Templates** - Pre-built templates for all note types
- **🌐 Local-First** - All data stored in markdown files you own

## 🚀 Quick Start

### 1. Install Required Plugins

**Core Plugin:**
- ✅ Bases (Built-in, enable in Settings → Core plugins)

**Community Plugins:**
- 🔧 Templater
- 🎯 Buttons
- 📊 Dataview (optional)
- 🏠 Homepage (optional)

### 2. Copy Files to Your Vault

```
Your Vault/
├── Command-Center-Dashboard.md
├── Templates/
│   ├── Project-Template.md
│   ├── Area-Template.md
│   ├── Task-Template.md
│   ├── Resource-Template.md
│   ├── Idea-Template.md
│   ├── Friend-Template.md
│   └── Prompt-Template.md
├── Bases/
│   ├── Projects-DB.base
│   ├── Areas-DB.base
│   ├── Resources-DB.base
│   ├── All-Tasks-DB.base
│   └── Simple-Notes-DB.base
└── .obsidian/snippets/
    └── command-center.css
```

### 3. Create Folders

Create these folders in your vault:
- `Projects/`
- `Areas/`
- `Resources/`
- `Tasks/`
- `Notes/`

### 4. Enable CSS Snippet (Optional)

1. Copy `command-center.css` to `.obsidian/snippets/`
2. Go to Settings → Appearance → CSS snippets
3. Enable "command-center"

## 📚 Database Structure

### Projects Database
Manage all your projects with status tracking, priorities, and progress.

**Properties:**
- `status`: Todo | In Progress | Done | Archived
- `priority`: High | Medium | Low
- `area`: Link to related area
- `due-date`: Project deadline
- `progress`: 0-100%

### Areas Database
Track areas of responsibility using the PARA method.

**Properties:**
- `type`: Personal | Work | Learning | Health
- `projects`: Links to related projects
- `last-reviewed`: Review date
- `goals`: Area goals

### Resources Database
Centralize articles, books, videos, and tools.

**Properties:**
- `category`: Article | Book | Video | Course | Tool
- `rating`: 0-5 stars
- `url`: Link to resource
- `status`: To Read | Reading | Done

### Tasks Database
All your tasks with project and area relationships.

**Properties:**
- `task-name`: Task title
- `project`: Link to parent project
- `status`: Todo | In Progress | Done
- `priority`: High | Medium | Low
- `due-date`: Task deadline
- **`project-status`**: Rollup from project (automatically synced)

## 🔗 Relational Database Features

### How Relationships Work

The system uses Obsidian's linking and Bases formulas to create relationships:

**1. Direct Links** (Many-to-One)
```yaml
project: "[[My Project]]"
area: "[[Work Area]]"
```

**2. Lists** (Many-to-Many)
```yaml
projects:
  - "[[Project A]]"
  - "[[Project B]]"
tags:
  - tag1
  - tag2
```

**3. Rollups** (Display Related Data)
```yaml
# In a Base formula:
project-status: this.project.status
```

### Example Workflow

1. **Create an Area:** "Work"
2. **Create a Project:** Link to "Work" area
3. **Create Tasks:** Link to project
4. **View in Tasks DB:** See project status automatically via rollup

## 🎨 Customization

### Adding Custom Properties

Edit templates to add your own properties:

```yaml
---
custom-field: value
my-rating: 5
project-code: ABC-123
---
```

### Creating Custom Views

Create new `.base` files with custom filters:

```yaml
name: High Priority Projects
source:
  type: folder
  path: Projects
filters:
  - type: property
    property: priority
    operator: is
    value: High
  - type: property
    property: status
    operator: is
    value: In Progress
```

### Styling the Dashboard

Edit `command-center.css` to customize colors, spacing, and layout.

## 📖 Documentation

- **[SETUP-GUIDE.md](SETUP-GUIDE.md)** - Detailed installation and configuration guide
- **[Obsidian Bases Documentation](https://help.obsidian.md/bases)** - Official Bases documentation
- **[Templater Documentation](https://silentvoid13.github.io/Templater/)** - Templater syntax and features

## 🆚 Obsidian Bases vs Notion Databases

| Feature | Obsidian Bases | Notion |
|---------|---------------|---------|
| **Local Storage** | ✅ Markdown files | ❌ Cloud only |
| **Relational Data** | ✅ Links + Rollups | ✅ Relations |
| **Performance** | ⚡ Fast (local) | 🐌 Can be slow |
| **Offline Access** | ✅ Full access | ⚠️ Limited |
| **Privacy** | ✅ Complete | ⚠️ Cloud-based |
| **Customization** | ✅✅ Unlimited | ⚠️ Limited |
| **Multiple Views** | ⚠️ Table + Card | ✅ Many views |
| **Learning Curve** | ⚠️ Moderate | ✅ Easy |

## 🎯 Use Cases

### Project Management
- Track multiple projects across different areas
- Manage tasks with priorities and deadlines
- Monitor progress with rollup properties

### Knowledge Management
- Organize resources by category and rating
- Link notes to projects and areas
- Track learning progress

### Personal Productivity
- Weekly planning with Make Time section
- Quick capture for ideas and contacts
- Dashboard overview of all activities

### Team Collaboration
- Share vault via Obsidian Sync
- Use consistent templates
- Track project dependencies

## 🔄 Upgrading from Dataview

If you're currently using Dataview:

1. **Keep using both:** Bases for editing, Dataview for complex queries
2. **Migrate gradually:** Convert one database at a time
3. **Leverage strengths:** Use Bases for tables, Dataview for custom layouts

## 🐛 Troubleshooting

### Bases not showing data?
- Check YAML frontmatter syntax
- Verify folder paths in `.base` files
- Ensure properties exist in source notes

### Rollups showing undefined?
- Verify linked notes exist
- Check property names match exactly
- Use proper link format: `[[Note Name]]`

### Buttons not working?
- Enable Buttons plugin
- Switch to Reading view
- Check button syntax

See [SETUP-GUIDE.md](SETUP-GUIDE.md) for more troubleshooting tips.

## 🤝 Contributing

Contributions welcome! Ideas for improvements:
- Additional templates
- Custom CSS themes
- New database views
- Documentation improvements

## 📜 License

MIT License - feel free to use and modify for your needs.

## 🙏 Acknowledgments

- **Obsidian Team** - For creating Bases and an amazing product
- **Community Plugin Developers** - Templater, Buttons, Dataview creators
- **Notion** - For pioneering database-in-notes concepts

## 📞 Support

- **Issues:** Submit via GitHub Issues
- **Questions:** Obsidian Forum or Discord
- **Updates:** Watch this repository for updates

## 🗺️ Roadmap

- [ ] Mobile-optimized layout
- [ ] Additional view types (calendar, timeline)
- [ ] More template examples
- [ ] Video tutorials
- [ ] Sample vault with demo data
- [ ] Integration with Tasks plugin

---

**Made with ❤️ for the Obsidian community**

*Last updated: November 2025*
