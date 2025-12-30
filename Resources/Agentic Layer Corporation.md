---
type: Resource
status: Active
source: YouTube
url: https://www.youtube.com/watch?v=fop_yxV-mPo
author: IndyDevDan
created: 2025-12-30
area: "[[AI]]"
tags:
  - ai
  - agentic-coding
  - claude-code
  - software-engineering
  - automation
  - mcp
  - tutorial
---

# Agentic Layer Corporation

## Summary

The **Agentic Layer** is the new outer ring around your codebase where you teach agents to operate your application on your behalf—potentially better than you or your team ever could. Building this layer is the highest ROI action for any engineer in the age of AI agents.

The ultimate goal is reaching the **Codebase Singularity**: the moment you trust your agents to run your codebase better than you can, where nothing ships to production without your teams of agents.

---

## Architecture Overview

```
┌─────────────────────────────────────────┐
│           AGENTIC LAYER                 │  ← Outer ring (green)
│  ┌───────────────────────────────────┐  │
│  │       APPLICATION LAYER           │  │  ← Inner layer (dark)
│  │  • Database                       │  │
│  │  • Frontend                       │  │
│  │  • Backend                        │  │
│  │  • Scripts                        │  │
│  │  • DevOps                         │  │
│  └───────────────────────────────────┘  │
└─────────────────────────────────────────┘
```

The agentic layer wraps around your application(s), enabling agents to see everything across multiple repositories.

---

## The Three Classes

| Class | Defining Element | Description |
|-------|------------------|-------------|
| **Class 1** | Commands & Memory | Foundation layer with prompts and basic agent capabilities |
| **Class 2** | Enhanced Tools | Expanded tooling and specialized workflows |
| **Class 3** | Multi-Agent Orchestration | Orchestrator agents controlling AI developer workflows |

---

## Class 1: Detailed Grade Breakdown

### Grade 1 - Thinnest Agentic Layer

**Components:**
- Prime prompt
- Memory files (CLAUDE.md)

**Folder Structure:**
```
project/
├── .claude/
│   └── commands/
│       └── prime.md          # Prime command/prompt
├── CLAUDE.md                  # Memory file (always loads)
└── src/                       # Application layer
```

**Advantages:**
- Clean, minimal setup
- Great foundation for agentic growth
- Agents understand context immediately

**Trade-offs:**
- Useless for large codebases
- Limited capability
- Misses many leverage points

---

### Grade 2 - Specialized Prompts & Sub-agents

**New Components:**
- Specialized planning prompts
- Sub-agents (agents)
- Specs directory for plans
- AI docs for agent context

**Folder Structure:**
```
project/
├── .claude/
│   ├── commands/
│   │   ├── prime.md
│   │   └── plan.md           # Planning prompt
│   └── agents/
│       ├── fetch-docs.md     # Documentation fetcher
│       └── test-writer.md    # Test writing agent
├── specs/                     # Planning documents
├── ai-docs/                   # Documentation for agents
├── CLAUDE.md
└── src/
```

**Advantages:**
- Specialization with sub-agents
- Parallelizable workflows
- Planned work before implementation

---

### Grade 3 - Custom Tools

**New Components:**
- Skills
- MCP servers
- Prime commands with tool access

**Folder Structure:**
```
project/
├── .claude/
│   ├── commands/
│   │   ├── prime.md
│   │   ├── plan.md
│   │   └── prime-db-with-tools.md   # Tool-enhanced prompt
│   ├── agents/
│   │   ├── fetch-docs.md
│   │   └── test-writer.md
│   └── skills/
│       ├── migrate-database.md      # DB migration skill
│       └── start-stop-app.md        # App control skill
├── mcp.json                          # MCP server config
├── specs/
├── ai-docs/
├── CLAUDE.md
└── src/
```

**Key Insight:** Skills and MCP servers can both be replaced with well-engineered prompts. The Core 4 matters most:
1. Context
2. Model
3. Prompt
4. Tools

**Common Pitfall:** Engineers have too many tools, burn cash, over-engineer tools that won't scale.

---

### Grade 4 - Closed-Loop Prompts

**New Components:**
- Higher-order prompts (plan, build, review)
- Feedback loops in codebase
- Self-correcting agents
- Review outputs directory

**Folder Structure:**
```
project/
├── .claude/
│   ├── commands/
│   │   ├── prime.md
│   │   ├── plan.md
│   │   ├── build.md              # Build prompt
│   │   ├── review.md             # Code review prompt
│   │   ├── test-backend.md       # Specialized testing
│   │   ├── test-frontend.md
│   │   └── reproduce-bug.md      # Bug reproduction
│   ├── agents/
│   │   ├── fetch-docs.md
│   │   ├── test-writer.md
│   │   └── review-agent.md       # Review agent
│   └── skills/
│       ├── migrate-database.md
│       └── start-stop-app.md
├── app-reviews/                   # Review outputs
│   └── [resolution files]
├── specs/
├── ai-docs/
├── CLAUDE.md
├── client/                        # Frontend app
└── server/                        # Backend app
```

**The Three-Step Workflow (Closed Loop):**
```
Request → Validate → Resolve
    ↑                    │
    └────────────────────┘
```

**Advantages:**
- Agents resolve their own work
- Specialized tasks per codebase area
- Self-correcting capabilities

---

### Grade 5 - Scaled Workflows

**Characteristics:**
- Many prompts, agents, and skills
- Multiple MCP servers
- Preparation for multi-agent orchestration (Class 2/3)

---

## Class 3: Orchestrator Systems

**Components:**
- Orchestrator agent
- AI developer workflows
- Multi-agent coordination

**Capabilities:**
- Plan → Build → Review → Fix cycles
- End-to-end autonomous workflows
- Parallel workflow execution
- Building entire applications in one shot

---

## Component Reference

### Commands
Raw prompts that activate specific agent behaviors.

| Type | Purpose | Example |
|------|---------|---------|
| Prime | Bootstrap agent context | `prime.md` |
| Plan | Strategic planning | `plan.md` |
| Build | Implementation | `build.md` |
| Review | Code review | `review.md` |
| Test | Testing specific areas | `test-backend.md` |

### Agents (Sub-agents)
Specialized agents for specific tasks.

| Agent | Purpose |
|-------|---------|
| Fetch Docs | Pull documentation into AI docs |
| Test Writer | Generate tests |
| Review Agent | Review code changes |

### Skills
Teaching agents how to use specific tools/scripts.

```markdown
# Example: Start/Stop Application Skill

## Tools Available
- `./scripts/start.sh` - Start the application
- `./scripts/stop.sh` - Stop the application

## Usage
When asked to start/stop the app, use these scripts.
```

### MCP Servers
External tool integrations via `mcp.json`:
- PostgreSQL
- Firecrawl
- Jira
- Notion
- GitHub

---

## Key Concepts

### Codebase Singularity
> "My agents can now run my codebase better than I can. I trust them to ship more than I trust myself or my team."

### Agentic Horizon
The future where your codebase runs itself—from prompt to production.

### Compute Advantage
Scaling compute = Scaling impact. Add more agent compute to get more confidence in results.

### Core 4
The fundamental elements of agentic systems:
1. **Context** - What the agent knows
2. **Model** - The AI model powering the agent
3. **Prompt** - Instructions for the agent
4. **Tools** - Actions the agent can take

---

## Progression Path

```
Grade 1: Memory + Prime Prompt
    ↓
Grade 2: + Sub-agents + Specs + AI Docs
    ↓
Grade 3: + Skills + MCP Servers + Tool Access
    ↓
Grade 4: + Closed-Loop Prompts + Feedback Loops
    ↓
Grade 5: + Scaled Workflows
    ↓
Class 3: Multi-Agent Orchestration
    ↓
🎯 Codebase Singularity
```

---

## Key Takeaways

1. **The agentic layer is the highest ROI investment** for any engineer in the age of AI
2. **Start simple** (Grade 1) and progressively add capability
3. **Closed-loop prompts are critical** - agents should review and fix their own work
4. **Don't over-engineer tools** - well-crafted prompts can replace many MCP servers
5. **The Core 4 matters most**: Context, Model, Prompt, Tools
6. **Feedback loops = More compute = Higher confidence** in agent results
7. **Specialize prompts** as your codebase grows (test-frontend, test-backend, etc.)

---

## Example Templates

> These examples are reconstructed from the patterns described in the video. Use them as starting points for your own agentic layer.

### Commands

#### prime.md
```markdown
# Prime Command

Read the following files to understand this codebase:

1. Read `CLAUDE.md` for project context and conventions
2. Read `specs/` directory for current project plans
3. Read `ai-docs/` for relevant documentation

## Your Role
You are an expert software engineer working on this codebase.
Follow the patterns and conventions established in the memory files.

## Before Starting Work
- Understand the existing architecture
- Review recent changes in git history
- Check for any active specs or plans
```

#### plan.md
```markdown
# Plan Command

Create a detailed implementation plan for the requested feature or fix.

## Process
1. Analyze the current codebase structure
2. Identify files that need modification
3. Consider edge cases and error handling
4. Break down into discrete, testable steps

## Output Format
Save your plan to `specs/[feature-name]-spec.md` with:
- Overview of changes
- Step-by-step implementation plan
- Files to be modified/created
- Testing strategy
- Potential risks or blockers

## Important
- Do NOT implement yet - only plan
- Ask clarifying questions if requirements are unclear
- Consider backwards compatibility
```

#### build.md
```markdown
# Build Command

Implement the feature according to the spec.

## Process
1. Read the relevant spec from `specs/`
2. Implement changes step by step
3. Follow existing code patterns
4. Add appropriate error handling
5. Write tests as you go

## Guidelines
- Keep changes focused and minimal
- Commit logical chunks of work
- Update documentation as needed
```

---

### Closed-Loop Prompts (Grade 4)

#### review.md
```markdown
# Code Review Command

Review all staged changes and provide feedback.

## REQUEST
1. Run `git diff --staged` to see all changes
2. Analyze code quality, patterns, and potential issues
3. Check for:
   - Security vulnerabilities
   - Performance concerns
   - Code style consistency
   - Missing error handling
   - Test coverage

## VALIDATE
- Verify changes match the original spec/intent
- Ensure no unintended side effects
- Check that tests pass: `npm test`
- Verify build succeeds: `npm run build`

## RESOLVE
If issues found:
1. Document issues in `app-reviews/review-[date].md`
2. Fix critical issues immediately
3. Re-run validation steps
4. Loop until all checks pass

Output final review summary to `app-reviews/review-[date].md`
```

#### test-backend.md
```markdown
# Test Backend Command

Run and validate all backend tests.

## REQUEST
Execute the backend test suite:
```bash
cd server && npm test
```

## VALIDATE
- All tests must pass
- Check test coverage meets threshold (>80%)
- Verify no skipped tests without justification

## RESOLVE
If tests fail:
1. Analyze failure output
2. Identify root cause
3. Fix the failing code or test
4. Re-run tests
5. Loop until all tests pass

Do not stop until all backend tests pass.
```

#### reproduce-bug.md
```markdown
# Reproduce Bug Command

Systematically reproduce and document a reported bug.

## REQUEST
1. Read the bug report/issue
2. Set up the reproduction environment
3. Follow steps to reproduce

## VALIDATE
- Confirm bug is reproducible
- Document exact reproduction steps
- Identify the root cause in code
- Determine affected code paths

## RESOLVE
1. Write a failing test that captures the bug
2. Fix the underlying issue
3. Verify the test now passes
4. Check for regression in related areas
5. Document resolution in `app-reviews/bug-[issue-id]-resolution.md`

Save resolution file with:
- Original bug description
- Root cause analysis
- Fix implemented
- Tests added
```

---

### Skills (Grade 3)

#### migrate-database.md
```markdown
# Skill: Database Migration

You have learned how to perform database migrations.

## Available Tools

### Create Migration
```bash
npm run db:migrate:create -- --name [migration_name]
```

### Run Migrations
```bash
npm run db:migrate:up
```

### Rollback Migration
```bash
npm run db:migrate:down
```

### Check Migration Status
```bash
npm run db:migrate:status
```

## Usage Guidelines
- Always check migration status before running new migrations
- Test migrations on a local database first
- Create rollback plan before applying to production
- Name migrations descriptively: `add_user_preferences_table`

## When to Use
Use this skill when asked to:
- Add new database tables
- Modify existing schema
- Add indexes or constraints
- Seed data
```

#### start-stop-app.md
```markdown
# Skill: Application Control

You have learned how to start and stop the application.

## Available Tools

### Start Application
```bash
./scripts/start.sh
```
Starts all services (frontend, backend, database).

### Stop Application
```bash
./scripts/stop.sh
```
Gracefully stops all running services.

### Restart Application
```bash
./scripts/stop.sh && ./scripts/start.sh
```

### Check Status
```bash
./scripts/status.sh
```

## Usage Guidelines
- Always check status before starting
- Use graceful stop to prevent data loss
- Wait for services to fully start before testing
- Check logs if startup fails: `./scripts/logs.sh`
```

#### prime-db-with-tools.md
```markdown
# Prime Command with Database Tools

Read memory files and prepare for database operations.

## Context Loading
1. Read `CLAUDE.md` for project context
2. Read `ai-docs/database-schema.md` for current schema

## Database CLI Tools
You can interact with the database using PSQL:

### Connect to Database
```bash
psql -h localhost -U app_user -d user_management
```

### Common Operations
```sql
-- List all tables
\dt

-- Describe table structure
\d users

-- Query data
SELECT * FROM users LIMIT 10;

-- Check indexes
\di
```

## Guidelines
- Always use transactions for write operations
- Back up data before destructive operations
- Use parameterized queries to prevent SQL injection
- Check query plans for performance: `EXPLAIN ANALYZE`
```

---

### Agents (Sub-agents)

#### fetch-docs.md
```markdown
# Agent: Documentation Fetcher

Fetch and organize documentation for agent consumption.

## Purpose
Pull relevant documentation from external sources and save to `ai-docs/`.

## Process
1. Identify required documentation based on task
2. Fetch from official sources (docs sites, GitHub, etc.)
3. Extract relevant sections
4. Format for agent consumption (concise, actionable)
5. Save to `ai-docs/[library-name].md`

## Output Format
```markdown
# [Library Name] - Quick Reference

## Installation
[installation commands]

## Common Usage
[most common patterns]

## API Reference
[key functions/methods]

## Gotchas
[common pitfalls to avoid]
```

## When to Invoke
- Before implementing with unfamiliar library
- When documentation is outdated in ai-docs
- When error messages reference unknown APIs
```

#### test-writer.md
```markdown
# Agent: Test Writer

Generate comprehensive tests for code changes.

## Purpose
Write tests that validate new or modified functionality.

## Process
1. Analyze the code to be tested
2. Identify test cases:
   - Happy path scenarios
   - Edge cases
   - Error conditions
   - Boundary values
3. Write tests following project conventions
4. Ensure tests are isolated and repeatable

## Test Structure
```typescript
describe('[Component/Function Name]', () => {
  describe('[method or scenario]', () => {
    it('should [expected behavior]', () => {
      // Arrange
      // Act
      // Assert
    });
  });
});
```

## Guidelines
- One assertion per test when possible
- Use descriptive test names
- Mock external dependencies
- Test behavior, not implementation
- Aim for >80% coverage on new code
```

#### review-agent.md
```markdown
# Agent: Code Reviewer

Perform automated code review on changes.

## Purpose
Review code changes and output structured feedback.

## Process
1. Get diff of changes: `git diff HEAD~1`
2. Analyze each file changed
3. Check against review criteria
4. Output review to `app-reviews/`

## Review Criteria
- [ ] Code follows project style guide
- [ ] No security vulnerabilities
- [ ] Error handling is appropriate
- [ ] Tests cover new functionality
- [ ] No hardcoded secrets or credentials
- [ ] Performance considerations addressed
- [ ] Documentation updated if needed

## Output Format
Save to `app-reviews/review-[branch]-[date].md`:
```markdown
# Code Review: [Branch Name]

## Summary
[Overall assessment]

## Files Reviewed
- [file1.ts] - [status: approved/needs-changes]
- [file2.ts] - [status: approved/needs-changes]

## Issues Found
### Critical
- [issue description and location]

### Suggestions
- [improvement suggestion]

## Verdict
[APPROVED / CHANGES REQUESTED]
```
```

---

### Class 3: Orchestrator Example

#### orchestrator.md
```markdown
# Orchestrator Agent

Coordinate multiple AI developer workflows.

## Available Workflows

### Plan-Build-Review-Fix
Complete development cycle:
1. `/plan` - Create implementation spec
2. `/build` - Implement the feature
3. `/review` - Review the changes
4. `/fix` - Address review feedback
5. Loop steps 3-4 until approved

### Quick Build
For small changes:
1. `/build` - Implement directly
2. `/review` - Quick validation

### Test Cycle
For test-driven development:
1. Write failing tests
2. Implement to pass tests
3. Refactor
4. Review

## Invoking Workflows
```
Run workflow: plan-build-review-fix
Directory: ./projects/user-auth
Prompt: Add password reset functionality
```

## Parallel Execution
Multiple workflows can run simultaneously:
- Workflow 1: Feature A in `/projects/feature-a`
- Workflow 2: Feature B in `/projects/feature-b`

Monitor all workflows via the orchestrator dashboard.
```

---

## Source

- **Video**: [The Codebase Singularity](https://www.youtube.com/watch?v=fop_yxV-mPo)
- **Channel**: IndyDevDan
- **Course**: Tactical Agentic Coding / Agentic Horizon
- **Duration**: 16 minutes
