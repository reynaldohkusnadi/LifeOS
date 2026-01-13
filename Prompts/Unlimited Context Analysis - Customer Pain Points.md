---
type: prompt
category: research-analysis
tags:
  - prompt
  - ai
  - customer-research
  - pain-points
  - context-management
  - long-form-analysis
created: 2026-01-13
modified: 2026-01-13
model: claude-sonnet-4-5
status: active
effectiveness: ⭐⭐⭐⭐⭐
source: https://www.youtube.com/watch?v=H-uwnpmziGA
---

# 🧠 Unlimited Context Analysis: Customer Pain Points

## Quick Reference Summary
**A technique for analyzing large collections of documents beyond Claude's context window.** Uses three persistent markdown files (context, todos, insights) that survive memory compaction, enabling iterative processing of unlimited files. Perfect for extracting customer pain points from meeting transcripts, interviews, or support tickets.

## Purpose
Enable Claude Code to analyze hundreds of documents systematically by maintaining state across context resets. The technique uses markdown files as persistent memory, allowing Claude to:
- Process more files than would fit in a single context window
- Track progress across multiple sessions
- Build cumulative insights iteratively
- Resume analysis after interruptions or memory compaction

Specifically designed for extracting customer pain points, questions, and concerns from transcripts to inform content creation and product development.

---

## The Core Technique: Unlimited Context via Markdown Files

### How It Works
1. **Context File:** Stores the goal and analysis criteria (read-only reference)
2. **Todos File:** Tracks which files have been processed and progress status
3. **Insights File:** Accumulates findings iteratively after each file
4. **Memory Compaction Safety:** Claude reads context + todos before continuing

### Why This Works
- Markdown files persist outside Claude's context window
- Each file processed adds to cumulative insights
- Progress tracking prevents duplicate work
- Context file keeps Claude aligned on goals after resets

---

## The Main Prompt

### When to Use
- Analyzing 10+ meeting transcripts or interview files
- Extracting patterns from customer feedback
- Processing large collections of support tickets
- Any analysis that exceeds single-context capacity
- Building research insights from multiple sources

### The Prompt

```
I want you to analyze all the meeting transcripts in this folder to find patterns in how clients describe their problems, what questions they ask, and what concerns they raise. If it does not cause frustration, stress, fear, or confusion, it does not count.

Before you start:
1. Create a context markdown file that contains the goal of this analysis: extracting customer pain points in their own words for future content creation
2. Create a todos markdown file to track which files you've analyzed and what you've found
3. Create an insights markdown file that you iteratively update after processing each transcript

As you work:
- Iteratively update the insights file after processing each transcript
- Check off each transcript in the todos as you complete them and make sure it's updated before your memory gets compacted
- After any memory compaction, read context and todos files before continuing

For each transcript, extract:
- Exact phrases used to describe problems or pain points
- Questions asked
- Concerns or hesitations mentioned

Work through all files until complete.
```

---

## File Structure Templates

### 1. Context File (`analysis-context.md`)

```markdown
# Analysis Context: Customer Pain Points

## Goal
Extract customer pain points, questions, and concerns from meeting transcripts to inform content creation strategy.

## Criteria for Pain Points
Pain points MUST demonstrate one of:
- Frustration
- Stress
- Fear
- Confusion

If it doesn't cause emotional distress, it doesn't count.

## What to Extract
1. **Exact phrases** used to describe problems
2. **Questions asked** by customers
3. **Concerns or hesitations** mentioned

## Output Format
- Direct quotes in "quotation marks"
- Context: [which transcript/customer]
- Category: [frustration/stress/fear/confusion]
```

### 2. Todos File (`analysis-todos.md`)

```markdown
# Analysis Progress Tracker

## Files to Process
- [ ] transcript-01-client-a.txt
- [ ] transcript-02-client-b.txt
- [ ] transcript-03-client-c.txt
- [ ] transcript-04-client-d.txt

## Processing Status
- **Total Files:** 4
- **Completed:** 0
- **Remaining:** 4
- **Current File:** None

## Completion Log
<!-- Update after each file -->
```

### 3. Insights File (`analysis-insights.md`)

```markdown
# Customer Pain Point Insights

## Patterns Identified
<!-- Updated iteratively after each transcript -->

### Frustration Patterns
- [Pattern 1]
- [Pattern 2]

### Common Questions
- [Question 1]
- [Question 2]

### Fear & Concerns
- [Concern 1]
- [Concern 2]

## Direct Quotes by Category

### Frustration
> "Quote here" - Client A, transcript-01

### Stress
> "Quote here" - Client B, transcript-02

### Fear
> "Quote here" - Client C, transcript-03

### Confusion
> "Quote here" - Client D, transcript-04

## Emerging Themes
<!-- Added as patterns become clear -->

## Content Opportunities
<!-- Ideas for blog posts, guides, FAQs based on pain points -->
```

---

## Variables/Parameters

### Required Customizations
- **[FOLDER PATH]:** Path to folder containing files to analyze
- **[FILE TYPE]:** Transcripts, interviews, support tickets, surveys, etc.
- **[EXTRACTION CRITERIA]:** What specifically to look for (pain points, feature requests, objections, etc.)

### Optional Customizations
- **File naming convention:** For context/todos/insights files
- **Analysis depth:** Quick scan vs. deep analysis per file
- **Output format:** Quotes, summaries, categorization scheme
- **Threshold criteria:** What qualifies as a "pain point"

---

## Example Usage

### Scenario: Analyzing 20 Sales Call Transcripts

#### Step 1: Give Claude the Prompt
```
I want you to analyze all the sales call transcripts in the /transcripts/sales-calls/ folder to find patterns in how prospects describe their problems, what questions they ask, and what concerns they raise. If it does not cause frustration, stress, fear, or confusion, it does not count.

[... rest of full prompt ...]
```

#### Step 2: Claude Creates Foundation Files
Claude will create:
- `sales-calls-context.md` - Analysis goal and criteria
- `sales-calls-todos.md` - List of 20 transcripts to process
- `sales-calls-insights.md` - Empty file ready for findings

#### Step 3: Iterative Processing
Claude processes each transcript:
1. Read transcript-01.txt
2. Extract pain points, questions, concerns
3. Update `sales-calls-insights.md` with findings
4. Check off transcript-01 in `sales-calls-todos.md`
5. Move to transcript-02.txt
6. Repeat

#### Step 4: After Memory Compaction
If Claude's context gets compacted at file 12/20:
1. Claude reads `sales-calls-context.md` (remembers the goal)
2. Claude reads `sales-calls-todos.md` (sees 12 done, 8 remaining)
3. Claude reads `sales-calls-insights.md` (has all findings so far)
4. Claude continues with transcript-13.txt

#### Step 5: Final Deliverable
At completion, you have:
- **Insights file** with all pain points categorized
- **Patterns** identified across 20 calls
- **Direct quotes** ready for content creation
- **Themes** for product/marketing decisions

---

## Effectiveness

- **Rating:** ⭐⭐⭐⭐⭐ (5/5 stars)
- **Works best with:**
  - Claude Sonnet 4.5 or Opus 4.5 (best context management)
  - Large document collections (10-100+ files)
  - Structured analysis tasks with clear criteria
  - Research projects requiring cumulative insights

- **Limitations:**
  - Requires Claude Code or similar environment with file system access
  - Manual setup of analysis framework
  - Claude must remember to update todos before context reset
  - Best for qualitative analysis, not quantitative calculations

## When This Technique Shines

| Use Case | Why It Works | Alternative |
|----------|--------------|-------------|
| 50+ meeting transcripts | Can't fit all in one context | Batch processing with summaries |
| Longitudinal research | Builds insights over time | Single-pass analysis (misses patterns) |
| Multi-session analysis | Survives interruptions | Start over each session |
| Pattern identification | Cumulative learning across docs | Analyze files in isolation |
| Qualitative research | Preserves exact quotes + context | Lossy summarization |

---

## Pro Tips

### Maximizing Success

1. **Clear Criteria First:** Define exactly what counts as a "finding" before starting
   ```markdown
   # Bad: "Find interesting things"
   # Good: "Extract only statements that express fear of making the wrong choice"
   ```

2. **Structured Insights File:** Use consistent formatting for easy parsing later
   ```markdown
   ### [Category]
   - **Finding:** [Description]
   - **Quote:** "[Exact words]"
   - **Source:** [File name]
   - **Theme:** [Recurring pattern]
   ```

3. **Checkpoint Reminders:** Add this to your prompt:
   ```
   After every 5 files, explicitly update the todos file and confirm your progress.
   ```

4. **Hierarchical Insights:** Structure insights file with layers
   ```markdown
   ## Level 1: Raw Quotes (all findings)
   ## Level 2: Categorized (by type)
   ## Level 3: Patterns (themes across files)
   ## Level 4: Strategic Insights (what it means)
   ```

5. **Resume Instructions:** If interrupted, tell Claude:
   ```
   Resume the analysis. First read analysis-context.md and analysis-todos.md,
   then continue with the next unchecked file.
   ```

### Common Pitfalls to Avoid

❌ **Don't:** Let Claude process all files without updating todos
✅ **Do:** Update todos after every single file

❌ **Don't:** Create insights file at the end
✅ **Do:** Update insights iteratively after each file

❌ **Don't:** Use vague criteria like "interesting things"
✅ **Do:** Use specific criteria with examples

❌ **Don't:** Forget to tell Claude to read context files after reset
✅ **Do:** Explicitly instruct reading context + todos before continuing

---

## Advanced Variations

### Variation 1: Multi-Pass Analysis
```
Pass 1: Extract all raw findings → raw-findings.md
Pass 2: Categorize findings → categorized-insights.md
Pass 3: Identify patterns → patterns-report.md
Pass 4: Generate recommendations → strategic-recommendations.md
```

### Variation 2: Comparative Analysis
```
Analyze competitor customer reviews vs. our customer reviews
- context-our-customers.md
- context-competitor-customers.md
- todos-our-reviews.md
- todos-competitor-reviews.md
- insights-comparison.md ← finds gaps and opportunities
```

### Variation 3: Time-Series Analysis
```
Track how pain points evolve over time
- insights-q1-2024.md
- insights-q2-2024.md
- insights-q3-2024.md
- insights-trends.md ← identifies changes over time
```

---

## Integration with LifeOS

### Recommended Workflow

1. **Start in Projects/**
   - Create project: "Customer Research Q1 2026"
   - Link to relevant Area (e.g., [[Product Development]])

2. **Store Raw Files in Resources/**
   - Create subfolder: `Resources/Transcripts-2026-Q1/`
   - Place all transcripts there

3. **Generate Analysis Files in Project Folder**
   - `Projects/Customer Research Q1 2026/analysis-context.md`
   - `Projects/Customer Research Q1 2026/analysis-todos.md`
   - `Projects/Customer Research Q1 2026/analysis-insights.md`

4. **Create Summary Resource Note**
   - Use findings to create: `Resources/Customer Pain Points Analysis - Q1 2026.md`
   - Tag with: `#customer-research`, `#product`, `#content-strategy`
   - Link to project: `project: "[[Customer Research Q1 2026]]"`

5. **Turn Insights into Tasks**
   - Create tasks for content pieces: `Tasks/Write blog post - [Pain Point].md`
   - Link to both project and insights resource

### Example Project Structure
```
Projects/
└── Customer Research Q1 2026/
    ├── analysis-context.md
    ├── analysis-todos.md
    ├── analysis-insights.md
    └── raw-transcripts/
        ├── call-01.txt
        ├── call-02.txt
        └── ...

Resources/
└── Customer Pain Points Analysis - Q1 2026.md ← Final deliverable

Tasks/
├── Write FAQ addressing top 5 pain points.md
├── Create case study for [concern].md
└── Update landing page copy with pain point language.md
```

---

## Related Prompts & Techniques

- **[[McKinsey-Style Consultant Framework]]** - For analyzing insights strategically
- **[[Extract PDF Design]]** - For processing PDF transcripts
- **Market research analysis** (to be created)
- **Content strategy generator** (to be created)
- **Feature prioritization from feedback** (to be created)

---

## Notes

### Why This Matters for Content Creation

Extracting pain points in customers' **own words** is gold for:
- **Blog post titles:** "I feel like I'm throwing money away" → "Stop Wasting Money on [X]"
- **Landing page copy:** Use exact phrases customers use to describe problems
- **FAQ sections:** Answer the actual questions prospects ask
- **Email sequences:** Address specific fears and concerns
- **Product positioning:** Highlight benefits that solve real frustrations

### The Power of Exact Phrases

Generic: "Our customers struggle with efficiency"
vs.
Exact quote: "I spend 3 hours every Friday just trying to reconcile spreadsheets and I want to scream"

The second becomes: **"Tired of Screaming at Spreadsheets? Automate Your Friday Reconciliation in 5 Minutes"**

### Iterative Updates Are Critical

Don't wait until the end to compile insights. Update after EACH file because:
- Patterns emerge gradually across files
- Early insights inform how you read later files
- You spot contradictions and nuances
- If Claude's context resets, you don't lose work

---

## Version History

- **v1.0** (2026-01-13): Initial version with core unlimited context technique
- **Source:** YouTube video technique for maintaining state across context resets
- **Future improvements:**
  - Add automation script for file setup
  - Create templates for different analysis types
  - Add example outputs from real analyses

---

*Created: 2026-01-13*
*This technique transforms Claude from a single-document analyzer into a multi-document research assistant with unlimited capacity.*
