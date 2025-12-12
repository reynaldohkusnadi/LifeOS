---
type: resource
category: Video
resource-type: YouTube Video
url: https://www.youtube.com/watch?v=s96JeuuwLzc
rating: 5
date-added: 2025-12-11
date-consumed: 2025-12-11
author: NetworkChuck
tags:
  - resource
  - n8n
  - claude-code
  - automation
  - vps
  - ssh
  - ai-agents
  - tutorial
  - video
  - youtube
status: Consumed
area: "[[AI]]"
related-to: []
created: 2025-12-11
modified: 2025-12-11
---

# Connect N8N with Claude Code on VPS

## Resource Information
- **Type:** YouTube Video
- **Category:** Tutorial
- **URL:** https://www.youtube.com/watch?v=s96JeuuwLzc
- **Author:** NetworkChuck
- **Rating:** 5/5
- **Status:** Consumed
- **Date Added:** 2025-12-11
- **Duration:** 17 minutes

## Summary

NetworkChuck demonstrates how to connect N8N (automation platform) with Claude Code using SSH, enabling N8N to orchestrate AI terminal agents. This gives N8N access to Claude Code's powerful context-aware capabilities, skills, and multi-agent deployment. The key insight is that SSH is the simplest and most elegant solution - N8N's SSH node connects to a server running Claude Code and executes commands in headless mode.

## Key Takeaways

1. **SSH is the secret** - Use N8N's SSH node to connect to any server running Claude Code, no complex HTTP wrappers needed
2. **Session IDs enable conversations** - Generate a UUID and pass it with `--session-id` to maintain context across multiple N8N workflow steps
3. **Claude Code handles complexity** - Keep N8N as a simple orchestrator while Claude Code manages the heavy lifting with skills and multi-agent deployment
4. **Token efficiency** - Uses your existing Claude Pro subscription, so heavy token usage is already paid for

## Step-by-Step Instructions

### Requirements

1. **N8N instance** - Self-hosted on a VPS (recommended: Hostinger)
2. **Claude Code** installed on a Linux server (can be same VPS or separate)
3. **Claude Pro subscription** (required for Claude Code)

### Step 1: Install Claude Code on Your Server

Install Claude Code on any Linux-based machine:
- Your Hostinger VPS (alongside N8N)
- A separate Ubuntu server
- Raspberry Pi
- Mac or Windows with WSL

### Step 2: Create N8N Workflow with SSH Node

1. Open N8N and create a **new workflow**
2. Add a **trigger node** (manual or webhook)
3. Add an **SSH node** (search for "SSH")
4. Select action: **Execute Command**

### Step 3: Configure SSH Credentials

1. In the SSH node, click **Credentials** dropdown
2. Click **Create new credential**
3. Enter your server details:
   - **Host:** Your server's IP address (public IP for VPS)
   - **Username:** Your SSH username
   - **Password** or **Private Key**
4. Click **Save**
5. Look for "Connection tested successfully"

### Step 4: Test Basic Commands

**Test SSH connection:**
```bash
hostname
```

**Test Claude Code installation:**
```bash
claude --version
```

### Step 5: Run Claude Code in Headless Mode

Use the `-p` flag (print mode) for headless execution:

```bash
claude -p "your prompt here"
```

**Example with directory context:**
```bash
cd /path/to/your/project && claude -p "analyze this codebase"
```

### Step 6: Enable Dangerous Mode for Full Access (Optional)

For full system access (skills, file editing, etc.):

```bash
claude --dangerously-skip-permissions -p "your prompt"
```

### Step 7: Manage Sessions for Conversations

To maintain context across multiple N8N steps:

**Generate a Session ID** using a Code node:
```javascript
// JavaScript code node
return {
  sessionId: crypto.randomUUID()
};
```

**First Claude Command** (with session ID):
```bash
claude -p "your prompt" --session-id {{ $json.sessionId }}
```

**Resume Session** (in subsequent nodes):
```bash
claude -r --session-id {{ $json.sessionId }} -p "follow-up question"
```

The `-r` flag resumes the previous session.

## Architecture

```
┌─────────────┐     SSH      ┌──────────────────┐
│   N8N       │─────────────▶│  Linux Server    │
│ (VPS)       │              │  with Claude Code│
│             │◀─────────────│                  │
│ Orchestrator│   Response   │  AI Agent        │
└─────────────┘              └──────────────────┘
```

## Quick Reference Commands

| Command | Purpose |
|---------|---------|
| `claude -p "prompt"` | Headless mode (print response) |
| `claude --version` | Check installation |
| `claude --session-id UUID` | Start new session |
| `claude -r --session-id UUID` | Resume session |
| `claude --dangerously-skip-permissions` | Full access mode |

## Benefits of This Approach

| Feature | Benefit |
|---------|---------|
| **Context** | Claude Code has access to local files/directories |
| **Skills** | Use custom Claude skills (markdown files defining capabilities) |
| **Multi-Agent** | Deploy multiple agents from a single prompt |
| **Sessions** | Maintain conversation context across workflow steps |
| **Token Efficiency** | Uses your Claude Pro subscription (already paid) |

## Example Use Cases

1. **Slack Integration** - Talk to Claude Code from your phone via Slack
2. **Network Monitoring** - Deploy agents to check WiFi, network performance, security
3. **IT Department Automation** - N8N as orchestrator, Claude Code as the IT team
4. **Homelab Management** - Monitor and manage servers remotely

## How to Apply

- Set up N8N on my VPS with SSH node connected to Claude Code
- Create a Slack workflow for mobile access to Claude Code
- Build automation workflows that leverage Claude Code's context and skills
- Use session IDs to maintain conversations in multi-step workflows

## Related Resources

- GitHub Guide: https://github.com/theNetworkChuck/n8n-claude-code-guide
- NetworkChuck Academy N8N Course: https://ntck.co/n8n_academy
- Why Claude Code is Great: https://youtu.be/MsQACpcuTkU

## Tags & Categories
**Topics:** N8N, Claude Code, SSH, Automation, VPS, AI Agents
**Area:** [[AI]]
**Projects Related:**
**Related Resources:**

## Review

**Would I recommend this?** Yes

**Who would benefit from this?** Anyone using N8N for automation who wants to add powerful AI capabilities, or Claude Code users who want to orchestrate their workflows remotely.

**When to revisit:** When setting up the N8N + Claude Code integration

---
*Resource added: 2025-12-11*
