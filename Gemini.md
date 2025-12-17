# Gemini.md

This file provides guidance for me, Gemini, when working in this repository. It is based on the information provided in `CLAUDE.md`.

## Repository Overview

This repository is an **Obsidian vault** that functions as a personal productivity system, similar to a Notion dashboard. It is built using local markdown files and Obsidian's native features.

**This is not a traditional software project.** It does not contain executable code, and there are no build, test, or compilation commands. All modifications involve editing markdown files, YAML configurations, and CSS.

## Core Architecture

### PARA Method
The vault is organized using the PARA method:
- **`Projects/`**: Active projects with clear goals.
- **`Areas/`**: Ongoing responsibilities.
- **`Resources/`**: Reference materials.
- **`Tasks/`**: Individual tasks.
- **`Notes/`**: General notes.

### Obsidian Bases
The database system is powered by Obsidian's native **Bases** feature.
- **`.base` files** located in the `Bases/` directory are YAML files that define database views.
- These views query YAML frontmatter from the markdown files within the PARA folders.
- They support sorting, filtering, and rollup formulas to display data from linked notes.

### Key Components
- **`Command-Center-Dashboard.md`**: The main UI, which embeds database views.
- **`Templates/`**: Contains templates for creating new notes (Projects, Tasks, etc.) using the **Templater** plugin.
- **`Bases/`**: Holds the `.base` database configurations.
- **`.obsidian/snippets/command-center.css`**: Provides custom styling for the dashboard.

## How to Modify the System

### Editing Templates
- To change the structure of a note type, edit the corresponding file in the `Templates/` folder.
- **Crucially**, use **Templater syntax** (e.g., `2025-12-17`), not standard JavaScript template literals.
- Ensure YAML frontmatter property names remain consistent, as they are case-sensitive.

### Editing Database Views
- To change how data is displayed, edit the `.base` files in the `Bases/` directory.
- This involves modifying the YAML structure to add or remove columns, change sorting, or update filters.
- Relationships are created using wiki-links (`[[Note Name]]`) in the YAML frontmatter and can be referenced in formulas using dot notation (e.g., `this.project.status`).

### AI-Powered Resource Capture
- The repository has an AI-powered "Second Brain" feature for capturing online content.
- The command `/capture-resource` (defined in `.claude/commands/capture-resource.md`) is used to fetch, summarize, and categorize content from URLs (YouTube, articles, etc.).
- This process creates a new markdown file in the `Resources/` directory, complete with summary, tags, and a link to the relevant `Area`.

## Key Rules & Constraints
- **Case-Sensitive Properties**: `status` and `Status` are different properties. Consistency is critical between templates and base configurations.
- **Wiki-Links**: All links between notes in YAML frontmatter must use the `[[Note Name]]` format.
- **No Build Process**: Changes are live as soon as files are saved. Styling changes might require toggling the CSS snippet in Obsidian's settings.
- **Primary Plugins**: The core functionality relies on the **Bases** (core plugin) and **Templater** (community plugin).
