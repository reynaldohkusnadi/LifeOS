---
type: video
source: youtube
url: https://www.youtube.com/watch?v=g-JgaoheyTo
author: David Ondrej
created: 2025-12-14
area: "[[AI]]"
tags:
  - ai
  - claude-code
  - saas
  - deployment
  - vps
  - dokploy
  - prompt-engineering
  - full-stack
status: Captured
---

# How To Build & Deploy an AI SaaS End To End

## Summary

This comprehensive 52-minute tutorial demonstrates the complete process of building and deploying a production-ready AI SaaS application from scratch using Claude Code with Opus 4.5. David Ondrej builds a prediction market platform (similar to Polymarket) and shows the entire workflow from initial prompt to live deployment on a self-hosted VPS.

The video is split into two major parts:
1. **Building (00:00 - 22:33)**: Strategic prompt engineering, multi-agent workflow, and iterative development
2. **Deployment (22:33 - 52:10)**: GitHub setup, VPS configuration, Dokploy deployment, and debugging

**Key Philosophy**: The video emphasizes that building an MVP is easy in 2025 - the real skill is deploying it, maintaining it, and getting paying customers. It shows how to use AI not just for coding, but for upskilling yourself.

## Key Takeaways

### Strategic Prompting
- **Split complex tasks into multiple prompts** rather than one-shot attempts (5 prompts for the entire app)
- **Prevent feature bloat** by explicitly stating boundaries in prompts
- **The fewer lines of code, the better** - simplicity is key
- Use AI agents like a 10x engineer: focused, minimal, strategic

### Multi-Model Approach
- **Claude Code (Opus 4.5)**: Core logic, backend, architecture decisions
- **Gemini 3 Pro**: Frontend design and UI improvements
- Use the best model for each specific task, not one-size-fits-all

### Tech Stack Decisions
- Research tech stack thoroughly BEFORE building (hardest to change later)
- Stick with mainstream frameworks (Next.js, PostgreSQL, Prisma) - better AI support
- Avoid esoteric tech stacks - they're not in training data
- Use AI (Perplexity, ChatGPT) to research best practices

### Deployment & Self-Hosting
- **Self-hosting on VPS is cheaper and more predictable** than Vercel/Netlify/Railway
- No surprise $300K bills from serverless platforms
- Tools like Dokploy + Hostinger make VPS management accessible
- You get full root access and control

### AI-Assisted Development Workflow
1. Use AI to upskill yourself (learn Prisma, Git, Docker concepts)
2. Ask "dumb questions" - understand what the code does
3. Screenshot errors and paste logs into AI for debugging
4. Learn fundamental commands even when using AI agents

### Problem-Solving Mindset
- Don't take errors personally - they're just problems to solve
- Use cutting-edge AI models to overcome blockers
- Think like an entrepreneur: focus on problem-solving
- The goal is shipping, not perfect code

## The 6-Part Prompt Framework (Shown at 2:33)

David breaks down his first prompt into 6 strategic parts:

### 1. **Broad Overview** (The "What" Before the "How")
Tell Claude Code what you're building in plain English. This prevents the AI from wandering off track.

**Example**: "Build a prediction market platform where users can bet on outcomes of yes/no questions."

### 2. **Features Scope** (Explicit Boundaries)
List exactly which features should be included. This prevents feature bloat and over-engineering.

**Example**:
- Yes/no questions
- Buying shares of outcomes
- Seeing live odds
- (Explicitly state what's OUT of scope too)

### 3. **Tech Stack** (Critical Constraint)
Specify the exact technologies. This is one of the few decisions you as a human should make because changing it later is painful.

**Example**:
- Frontend: Next.js with App Router, Tailwind
- Backend: Next.js API routes
- Database: PostgreSQL with Prisma ORM
- Deployment: Docker-ready

**Why**: Research this thoroughly with Perplexity/ChatGPT first. Changing tech stack mid-project is extremely difficult.

### 4. **Deployment Considerations**
State where and how this will be deployed so the AI doesn't choose incompatible dependencies.

**Example**: "This will be deployed on a VPS using Docker. Ensure the project works with Nixpacks."

**Why**: Prevents issues where local development works but deployment fails.

### 5. **First Action** (Start Point)
Explicitly tell the AI what to do first.

**Example**: "Start by creating the project structure and detailed README. Document the database schema and architecture."

### 6. **Don't Implement Yet**
Tell the AI to plan first, code later.

**Example**: "Don't implement yet. Just create the architecture, documentation, and prepare for the code that will come in the next prompt."

**Why**: Allows you to review the plan before hundreds of lines of code are written.

## Complete Prompt Sequence Used

### Prompt 1: Architecture & Planning
- Create folder structure
- Generate comprehensive README
- Document database schema
- Plan deployment strategy
- **Don't implement yet**

### Prompt 2: Frontend Shell
- Set up Next.js with App Router and Tailwind
- Create basic pages (home, market list, market detail, create market)
- Use mock data only
- No API integration yet

### Prompt 3: Database Setup
- Add PostgreSQL connection using Prisma
- Create schema from README
- Generate migrations
- Ensure database URL reads from environment variables

### Prompt 4: Backend API
- Build API routes (create market, get markets, place bets, market odds)
- Wire up Prisma to endpoints
- Provide curl test examples

### Prompt 5: Connect Frontend to Backend
- Wire frontend to API
- Make it functional end-to-end
- Basic styling polish
- "The fewer lines of code, the better"

## Technical Stack Used

| Layer | Technology | Why |
|-------|-----------|-----|
| Frontend | Next.js 14 (App Router) | Modern React framework, well-documented |
| Styling | Tailwind CSS | Utility-first, AI models know it well |
| Backend | Next.js API Routes | Unified codebase, simple deployment |
| Database | PostgreSQL | Industry standard, reliable |
| ORM | Prisma | Type-safe, AI-friendly syntax |
| Containerization | Docker | Standard deployment format |
| Build System | Nixpacks | Auto-detects and builds projects |
| Hosting | Hostinger VPS | Affordable ($5-7/mo), predictable costs |
| Deployment | Dokploy | Open-source Vercel alternative for VPS |
| Version Control | GitHub | Industry standard |

## Deployment Process (Self-Hosting)

### Why Self-Host?
1. **Predictable costs** - Fixed $5-7/month vs surprise Vercel bills
2. **24/7 functions** - No 60-second timeout limits
3. **Direct database connections** - No RLS policy complexity
4. **Full control** - Use any open-source tech
5. **Root access** - Complete flexibility

### Step-by-Step Deployment
1. **Set up VPS** - Hostinger KVM2 plan (~$7/mo)
2. **Install Dokploy** - One-click from Hostinger panel
3. **Connect GitHub** - Authorize Dokploy to access repo
4. **Configure Project** - Select branch, build type (Nixpacks)
5. **Add Database Service** - PostgreSQL in same project
6. **Set Environment Variables** - DATABASE_URL from internal connection
7. **Deploy** - Automatic build and deployment
8. **Get Free Domain** - Dokploy provides subdomain
9. **Debug with Logs** - View real-time deployment logs

### Common Deployment Issues
- Database not running (forgot to deploy it)
- Missing environment variables
- Prisma migrations not run on production
- Dependencies not installed (add to package.json)

## AI Development Best Practices

### Prompt Engineering
- **Be explicit about constraints** - "The fewer lines of code, the better"
- **Use XML tags for context** - Separate logs, code, instructions
- **Trigger deep thinking** - Use "ultra think" or "think harder" keywords
- **Ask for simplicity** - "Make your answer simpler and shorter"
- **Prevent overengineering** - Specify exactly what features to include

### Debugging Workflow
1. Screenshot the error
2. Copy terminal logs
3. Paste both into AI with context
4. Ask AI to explain root cause
5. Implement fix
6. Test and iterate

### Learning While Building
- Ask AI to explain unfamiliar concepts (Prisma, ORMs, etc.)
- Compare to things you know ("Is Prisma like SQLAlchemy?")
- Don't blindly copy code - understand what it does
- Build your mental model of the system

### Tool Selection
- **Claude Code + Opus 4.5**: Best for logic and architecture
- **Gemini 3 Pro**: Best for frontend design
- **Perplexity**: Best for research and comparisons
- **Cursor**: Good for inline completions
- Use specialized tools for specialized tasks

## Pro Tips

### Git & GitHub
- Learn the core 7-10 Git commands (add, commit, push, pull, log, status)
- Don't use spaces in file/folder names (use dashes or underscores)
- Always create .gitignore before first commit
- Never commit .env files (use .env.example)

### File Organization
- Keep prompts in a `/prompts` folder for documentation
- Name files sequentially (prompt_01.md, prompt_02.md)
- Maintain a comprehensive README
- Document your decisions

### AI Agent Configuration
- Set up `.claude/settings.json` with allowed commands
- Use auto-accept mode for faster iteration
- Whitelist safe terminal commands (mkdir, npm, git)
- Deny dangerous commands (rm -rf, sudo)

### Cost Optimization
- Self-hosting: ~$7/month fixed cost
- Vercel Hobby: Free but severe limits
- Vercel Pro: Can balloon to thousands
- Supabase: Scales with usage
- **Winner**: VPS for predictable costs

## Timestamps

| Time | Topic |
|------|-------|
| 00:00 | Introduction |
| 00:46 | Starting a Project with Claude Code |
| 01:38 | Creating the First Prompt ⭐ |
| 10:52 | Testing the Frontend |
| 15:17 | Understanding Prisma and SQLAlchemy |
| 18:22 | Addressing Frontend Errors |
| 19:44 | Running the App and Testing |
| 22:33 | Connecting to GitHub |
| 30:34 | Deploying the Project |
| 33:12 | Introduction to Dokploy |
| 34:11 | Setting Up Server with Hostinger |
| 39:38 | Preparing for Deployment |
| 50:31 | Testing the Deployed App |

## Related Concepts
- [[Prompt Engineering]]
- [[AI-Assisted Development]]
- [[Self-Hosting]]
- [[VPS Management]]
- [[Full-Stack Development]]

## Action Items
- [ ] Set up `.claude/settings.json` with allowed commands
- [ ] Create prompt templates using the 6-part framework
- [ ] Research VPS hosting options (Hostinger vs alternatives)
- [ ] Learn basic Git commands (7-10 core commands)
- [ ] Try Dokploy for next deployment project

## Questions to Explore
- How does Dokploy compare to Coolify or CapRover?
- What are the limitations of Nixpacks vs custom Dockerfiles?
- When should you use multiple models vs single model?
- How to set up CI/CD with Dokploy?
