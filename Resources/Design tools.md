---
title: Design tools
type: Video
source: YouTube
url: https://www.youtube.com/watch?v=61Z2jLH4yGU
author: AI LABS
created: 2025-01-02
area: "[[AI]]"
status: Active
tags:
  - ai
  - design
  - web-development
  - figma
  - claude-code
  - workflow
  - tools
  - video
  - youtube
---

# Design tools

## Video Summary: "The Greatest Design System I've Ever Used"

**Channel:** AI LABS
**Duration:** 7 minutes
**Topic:** AI design tools that transform the website development workflow

The video covers AI-powered tools across four categories: planning, asset generation, animation, and design conversion. The presenter shares tools that made a real impact on their design process.

---

## Tools & Capabilities

### 1. Design OS (Planning)

| Attribute | Details |
|-----------|---------|
| **URL** | https://buildermethods.com/design-os |
| **Price** | Free (Open Source) |
| **Purpose** | Transform messy ideas into structured technical blueprints |

**Capabilities:**
- Mimics software development workflow (you act as stakeholder)
- Handles product planning, design system, and requirement specifications
- Asks structured questions to identify project details
- Exports technical plans with data models, TypeScript types, CSS tokens, sample data, and documentation
- Compatible with Claude Code, Cursor, and Copilot
- Provides step-by-step commands at localhost:3000

---

### 2. Vizcom (Asset Generation)

| Attribute | Details |
|-----------|---------|
| **URL** | https://www.vizcom.com/ |
| **Price** | Freemium (generous free tier) |
| **Purpose** | Generate professional product visuals |

**Capabilities:**
- Generate stunning visual imagery from prompts
- Create renders from sketches
- 3D modeling capabilities
- Generate animations
- Edit individual elements with AI
- Download results in 4K quality
- Great for hero section visuals

---

### 3. Google Mixboard (Asset Generation - Free Alternative)

| Attribute | Details |
|-----------|---------|
| **URL** | https://mixboard.google.com/projects |
| **Price** | Free (experimental) |
| **Purpose** | Create mood boards and generate images |

**Capabilities:**
- Uses Google's Nano Banana AI for image generation
- Modify images with prompts
- Upload sample images to generate matching visuals
- Unlimited generations
- Build full presentations for product concepts
- Regenerate, duplicate, or annotate images for more direction
- Download assets directly for website use

---

### 4. GoFullPage (Competitor Analysis)

| Attribute | Details |
|-----------|---------|
| **Price** | Free (Browser Extension) |
| **Purpose** | Capture full-page screenshots of websites |

**Capabilities:**
- Captures complete website screenshots
- Useful for competitor analysis
- Screenshots can be fed to Claude to extract UI elements, constraints, object placements, and theme details

---

### 5. Magic Animator (Animation)

| Attribute | Details |
|-----------|---------|
| **URL** | https://magicanimator.com/ |
| **Price** | Paid |
| **Purpose** | AI-powered animation for designs |

**Capabilities:**
- Animate logos, social media posts, and user interfaces
- Create micro-interactions for user retention
- Available as Figma plugin
- Auto-detects layers in UI designs
- Generates 4 animation options to choose from
- Exports as Lottie (JSON) format

---

### 6. LottieFiles (Animation - Free Alternative)

| Attribute | Details |
|-----------|---------|
| **URL** | https://lottiefiles.com/plugins/figma |
| **Price** | Free |
| **Purpose** | Implement animations in website designs |

**Capabilities:**
- Figma plugin for adding animations
- Export in multiple formats (various Lottie JSON files)
- Animation files can be given to Claude Code to apply to UI

---

### 7. HTML to Design (Design Conversion)

| Attribute | Details |
|-----------|---------|
| **URL** | https://html.to.design/home |
| **Price** | Freemium (10 imports/30 days on free plan) |
| **Purpose** | Convert HTML websites to editable Figma designs |

**Capabilities:**
- Convert any website to fully editable Figma design
- **MCP integration** - connect directly to Claude or Cursor
- Use keywords "send to Figma" or "send to HTML to design" in prompts
- Generates JSON containing design and sends to Figma
- Real-time collaboration between AI tools and Figma

---

## Step-by-Step Guides

### 1. Design OS Setup & Usage

**Installation:**
1. Copy the git clone command from the GitHub repository
2. Paste it into your project folder
3. Change the default name to your actual project name

**Usage:**
1. Navigate to `localhost:3000` after installation
2. Follow the listed steps one by one (commands are shown in order)
3. Answer the series of questions about your project idea
4. Review and approve the plan as it refines midway
5. Continue through all sections until the plan is ready
6. Export the final plan

**Exported Plan Contains:**
- Instructions on how to use it
- Data models
- Sample data
- Documentation
- TypeScript types
- CSS tokens
- Design files

**Building from Export:**
- Choose either **incremental method** OR **oneshot prompt** to build the app

---

### 2. Vizcom Asset Generation

1. Provide a sketch of your product
2. Add a description/prompt
3. AI generates visuals based on your input
4. Edit individual elements using AI modification tools
5. Download results in 4K quality for hero section visuals

---

### 3. Google Mixboard Usage

1. Create a new project/mood board
2. Use prompts to generate images for your website
3. (Optional) Upload sample images for the AI to generate matching visuals
4. If you don't like an image:
   - Regenerate it
   - Ask model to create similar images
   - Duplicate an image
   - Annotate it to give more direction
5. Download assets for use on your website

---

### 4. Competitor Analysis Workflow

1. Install **GoFullPage** browser extension
2. Navigate to competitor websites
3. Capture full-page screenshots using the extension
4. Provide screenshots to Claude with a specialized prompt:
   > *"Extract all UI elements including constraints, object placements, and UI theme details from these images"*
5. Claude extracts comprehensive UI style details
6. Provide the extracted style guidelines to **Claude Code** in your project folder (along with downloaded assets)
7. Claude generates the entire website applying all extracted styles and design guidelines

---

### 5. Magic Animator Workflow

1. Open your UI design in Figma
2. Run the Magic Animator plugin
3. Plugin auto-detects layers in your UI
4. Choose from 4 generated animation options
5. Export chosen animation as **Lottie file** (JSON format)
6. Give the animation file to Claude Code
7. Claude applies the animation to your UI

---

### 6. LottieFiles Alternative

1. Install LottieFiles Figma plugin
2. Implement animations in your website designs
3. Export in your preferred format (various Lottie JSON options)
4. Provide animation file to Claude Code for implementation

---

### 7. HTML to Design + MCP Integration

**Setup:**
1. Install HTML to Design Figma plugin
2. Connect it to your AI tools (Claude or Cursor)
3. Configure the MCP by following the setup guide

**Usage:**
1. Prompt your AI agent with your design request
2. Use keyword: **"send to Figma"** or **"send to HTML to design"**
3. AI generates a JSON containing the design
4. JSON is sent to Figma automatically
5. Approve the design in Figma
6. View and edit the design in Figma
7. Collaborate with AI tool to refine - edit anything you don't like on the fly

---

## Complete End-to-End Workflow

```
1. PLANNING
   └── Design OS → Structure ideas into technical specs

2. COMPETITOR ANALYSIS
   └── GoFullPage + Claude → Extract UI patterns

3. ASSET GENERATION
   └── Vizcom OR Mixboard → Create product visuals

4. BUILD
   └── Claude Code → Generate website with specs + assets

5. ANIMATE
   └── Magic Animator OR LottieFiles → Add micro-interactions

6. ITERATE
   └── HTML to Design + MCP → Edit in Figma, sync with AI
```

---

## Key Takeaways

- **Design OS** is the missing planning piece for AI-assisted web development
- Use **free alternatives** (Mixboard, LottieFiles) when paid tools aren't necessary
- **Competitor analysis** with GoFullPage + Claude extracts UI patterns efficiently
- **MCP integration** with HTML to Design enables real-time AI-Figma collaboration
- Combine these tools for a complete end-to-end AI design workflow
