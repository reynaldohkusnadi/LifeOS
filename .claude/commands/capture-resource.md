# Second Brain Resource Capture

Process a URL or document and create a structured resource note in LifeOS.

## How to Use
User provides: URL (YouTube, web article, Twitter) or file path (PDF)
Claude will: Extract content, summarize, categorize, and create a properly formatted resource note.

---

## Content Type Detection

Detect content type from URL pattern:
- **YouTube**: `youtube.com/watch`, `youtu.be/`
- **Twitter/X**: `twitter.com`, `x.com`
- **PDF**: `.pdf` file extension
- **Web Article**: All other URLs

---

## Processing Steps

### 1. YouTube Videos
1. Extract video ID from URL
2. Use `youtube_transcript` MCP or `mcp__MCP_DOCKER__fetch` to get transcript
3. Summarize key points from transcript
4. Set `category: Video`, `resource-type: YouTube Video`

### 2. Web Articles
1. Use `mcp__MCP_DOCKER__fetch` to get page content as markdown
2. Extract title, author if available
3. Summarize main points
4. Set `category: Article`, `resource-type: Web Article`

### 3. PDFs
1. Use Read tool to read PDF content
2. Summarize key sections
3. Set `category: Article` or `Book`, `resource-type: PDF Document`

### 4. Twitter/X
1. Use `mcp__MCP_DOCKER__fetch` to get tweet/thread content
2. Extract key points
3. Set `category: Article`, `resource-type: Twitter Thread`

---

## Categorization Guide

### Category Values (pick one):
| Category | When to Use |
|----------|-------------|
| Video | YouTube, Vimeo, educational videos |
| Article | Blog posts, news, essays, web content |
| Book | Book summaries, ebook content |
| Paper | Research papers, academic content |
| Tool | Software, apps, utilities |
| Course | Online courses, tutorials |
| Thread | Twitter threads, forum discussions |

### Resource-Type Values:
- YouTube Video
- Web Article
- Blog Post
- Twitter Thread
- PDF Document
- Research Paper
- Newsletter
- Book Summary

---

## Area Detection

Map content topics to existing Areas:

| If content is about... | Link to Area |
|------------------------|--------------|
| AI, machine learning, LLMs, AGI, automation, agents | `[[AI]]` |
| Investing, money, economics, crypto, markets | `[[Finance]]` |
| Education, skill development, knowledge management | `[[Learning]]` |
| Startups, entrepreneurship, business strategy, products | `[[Big Beautiful Business Idea]]` |
| Tennis technique, matches, equipment | `[[Tennis]]` |
| Fitness, workouts, health, nutrition | `[[Gym]]` |

If content doesn't clearly fit, leave `area:` empty.

---

## Tag Generation Strategy

Generate 4-6 tags using this hierarchy:

### 1. Always include:
- `resource` (required for all resources)

### 2. Domain Tag (1-2, broad category):
`ai`, `finance`, `learning`, `business`, `fitness`, `tennis`

### 3. Topic Tags (2-3, specific concepts):
Examples:
- AI topics: `machine-learning`, `llm`, `agentic-workflow`, `automation`, `prompt-engineering`
- Business topics: `startup`, `entrepreneurship`, `marketing`, `growth`, `strategy`
- Finance topics: `investing`, `crypto`, `wealth`, `economics`
- Learning topics: `productivity`, `habits`, `systems`, `knowledge-management`

### 4. Format Tag (1):
`video`, `article`, `tutorial`, `research`, `thread`

### 5. Source Tag (optional):
`youtube`, `twitter`, `substack`, `arxiv`, `github`

**Tag Rules:**
- Use lowercase
- Use hyphens for multi-word: `agentic-workflow` not `AgenticWorkflow`
- Match existing tags in vault when possible
- Keep tags specific enough to be useful for graph connections

---

## Note Output Format

Write to: `Resources/{Title}.md`

Use this exact YAML frontmatter structure:
```yaml
---
type: resource
category: {Category}
resource-type: {Resource-Type}
url: {URL}
rating: 0
date-added: {YYYY-MM-DD}
date-consumed:
author: {Author if known}
tags:
  - resource
  - {domain-tag}
  - {topic-tag-1}
  - {topic-tag-2}
  - {format-tag}
status: To Read  # or "To Watch" for videos
area: "[[{Area}]]"
related-to: []
created: {YYYY-MM-DD}
modified: {YYYY-MM-DD}
---
```

### Note Body Structure:
```markdown
# {Title}

## Resource Information
- **Type:** {Resource-Type}
- **Category:** {Category}
- **URL:** {URL}
- **Author:** {Author}
- **Rating:** (0/5)
- **Status:** To Read/To Watch
- **Date Added:** {YYYY-MM-DD}

## Summary
{2-3 sentence overview of what this resource covers}

## Key Takeaways
1. {Main point 1}
2. {Main point 2}
3. {Main point 3}
{Add more if valuable, max 5}

## Highlights & Notes

### Important Points
- {Key insight 1}
- {Key insight 2}
- {Key insight 3}

### Quotes
> {Notable quote if any}

### Personal Insights
{Any personal observations or connections to other knowledge}

## How to Apply
- {Actionable item 1}
- {Actionable item 2}

## Related Resources
- {Links to related resources if known}

## Tags & Categories
**Topics:** {Comma-separated topic list}
**Area:** `= this.area`
**Projects Related:** {Links to relevant projects if any}

## Review

**Would I recommend this?** Yes/No

**Who would benefit from this?** {Target audience}

**When to revisit:** {Suggestion}

---
*Resource added: {YYYY-MM-DD}*
```

---

## Example Output

For URL: `https://www.youtube.com/watch?v=hwTz4s_IqgE`

**File:** `Resources/Agentic Workflow Tutorial - Browser Automation.md`

```yaml
---
type: resource
category: Video
resource-type: YouTube Video
url: https://www.youtube.com/watch?v=hwTz4s_IqgE
rating: 0
date-added: 2025-12-10
date-consumed:
author:
tags:
  - resource
  - ai
  - agentic-workflow
  - automation
  - video
  - tutorial
status: To Watch
area: "[[AI]]"
related-to: []
created: 2025-12-10
modified: 2025-12-10
---
```
