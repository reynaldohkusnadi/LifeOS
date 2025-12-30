---
type: Github Repo
status: Active
created: 2025-12-19
source: https://github.com/AndyMik90/Auto-Claude
area: "[[AI]]"
tags:
  - ai
  - automation
  - claude
  - coding-assistant
  - developer-tools
  - open-source
  - agent-orchestration
  - electron
  - python
---

# Auto Claude - Free Agent Orchestration App

## Summary

Auto Claude is a free, open-source desktop application that supercharges AI coding workflows by running multiple autonomous Claude Code agents in parallel. It's designed for both beginners ("vibe coders") and experienced developers. The app uses git worktrees to isolate each task in a safe workspace, allowing developers to describe what they want built while agents handle planning, coding, and validation autonomously—achieving up to **10x output** while maintaining code quality.

## Key Features

| Feature | Description |
|---------|-------------|
| **Parallel Agents** | Run up to 12 simultaneous agent terminals with smart naming based on context |
| **Context Engineering** | Agents analyze your codebase structure before writing any code |
| **Self-Validating QA** | Built-in QA loop catches issues before you review (up to 50 iterations) |
| **Git Worktree Isolation** | All work happens in isolated branches—your main stays safe until merge |
| **AI Merge Resolution** | Intelligent 3-tier conflict resolution (~98% prompt reduction) |
| **Memory Layer** | Graph database (FalkorDB + Graphiti) remembers insights across sessions |
| **Cross-Platform** | Desktop app runs on Mac, Windows, and Linux |
| **Any Project Type** | Works with web apps, APIs, CLIs—any software project |

## How It Works

### Phase 1: Spec Creation (3-8 phases)

Before any code is written, agents gather context:

1. **Discovery** — Analyzes project structure and tech stack
2. **Requirements** — Gathers what you want to build through conversation
3. **Research** — Validates external integrations against real documentation
4. **Context Discovery** — Finds relevant files in your codebase
5. **Spec Writer** — Creates comprehensive specification document
6. **Spec Critic** — Self-critiques using extended thinking to find issues early
7. **Planner** — Breaks work into subtasks with dependencies
8. **Validation** — Ensures all outputs are valid before proceeding

### Phase 2: Implementation

1. **Planner Agent** — Creates subtask-based implementation plan
2. **Coder Agent** — Implements subtasks one-by-one with verification
3. **QA Reviewer** — Validates all acceptance criteria
4. **QA Fixer** — Self-healing loop (up to 50 iterations)

Each session runs with a fresh context window. Progress tracked via `implementation_plan.json` and Git commits.

### Phase 3: Merge

1. **Conflict Detection** — Identifies files modified in both main and the build
2. **3-Tier Resolution** — Git auto-merge → Conflict-only AI → Full-file AI (fallback)
3. **Parallel Merge** — Multiple files resolve simultaneously
4. **Staged for Review** — Changes staged but not committed for your review

> A build 50+ commits behind main merges in seconds instead of manual conflict resolution.

## Desktop UI Features

- **Kanban Board** — Visual task management from "Planning" to "Done"
- **Agent Terminals** — Spawn up to 12 AI-powered terminals with one-click context injection
- **Insights** — ChatGPT-style interface for project conversations
- **Roadmap** — AI-generated feature prioritization based on target audience
- **Ideation** — Discover improvements, bottlenecks, vulnerabilities, documentation gaps
- **Changelog** — Auto-generate professional release notes from completed tasks
- **Context View** — See exactly what Auto Claude understands about your project

## Memory Layer Architecture

The Memory Layer is a **hybrid RAG system** combining graph nodes with semantic search:

| Setup | LLM | Embeddings | Notes |
|-------|-----|------------|-------|
| **OpenAI** | OpenAI | OpenAI | Simplest - single API key |
| **Anthropic + Voyage** | Anthropic | Voyage AI | High quality |
| **Ollama** | Ollama | Ollama | Fully offline |
| **Azure** | Azure OpenAI | Azure OpenAI | Enterprise |

## Prerequisites

- Node.js 18+
- Python 3.9+
- Docker Desktop (for FalkorDB Memory Layer)
- Claude Code CLI (`npm install -g @anthropic-ai/claude-code`)
- **Claude Pro or Max subscription** (required for Claude Code access)
- Git repository (Auto Claude uses git worktrees for isolation)

## Quick Start

```bash
# 1. Set up Python backend
cd auto-claude
uv venv && uv pip install -r requirements.txt

# 2. Start Memory Layer
docker-compose up -d falkordb

# 3. Install and launch Desktop UI
cd auto-claude-ui
pnpm install && pnpm run build && pnpm run start
```

## Security Model

Three-layer defense keeps your code safe:

1. **OS Sandbox** — Bash commands run in isolation
2. **Filesystem Restrictions** — Operations limited to project directory
3. **Command Allowlist** — Only approved commands based on your project's stack

## Project Structure

```
your-project/
├── .worktrees/               # Isolated workspace (git-ignored)
├── .auto-claude/             # Per-project data (specs, plans, QA reports)
│   ├── specs/                # Task specifications
│   ├── roadmap/              # Project roadmap
│   └── ideation/             # Ideas and planning
```

## License

**AGPL-3.0** — Requires open-sourcing derivative works. Closed-source commercial usage requires separate license.

## Links

- [GitHub Repository](https://github.com/AndyMik90/Auto-Claude)
- [Discord Community](https://discord.gg/maj9EWmY)
- [CLI Usage Guide](https://github.com/AndyMik90/Auto-Claude/blob/main/guides/CLI-USAGE.md)
- [Docker Setup Guide](https://github.com/AndyMik90/Auto-Claude/blob/main/guides/DOCKER-SETUP.md)

## Why This Matters

Auto Claude represents a significant shift in AI-assisted development:
- **Context-aware**: Understands your codebase before writing code
- **Self-correcting**: QA loop catches issues before human review
- **Safe by design**: Git worktrees prevent damage to main branch
- **Memory persistence**: Agents get smarter across sessions

Perfect for developers who want to scale their output without sacrificing code quality.
