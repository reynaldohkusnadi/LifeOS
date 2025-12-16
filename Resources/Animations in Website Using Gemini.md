---
type: video
source: youtube
url: https://www.youtube.com/watch?v=tFqMpi7KuzI
author: Andy Lo
created: 2025-12-17
status: Saved
area: "[[AI]]"
tags:
  - ai
  - web-design
  - gemini
  - no-code
  - animation
  - google-ai
  - firebase
  - personal-branding
  - video
  - tutorial
---

# Animations in Website Using Gemini

## Overview
**Video Title:** How I Built a Cinematic Personal Website with Google Gemini Free AI Tools In 10 Mins [No-Code]
**Author:** Andy Lo
**Duration:** 13 minutes
**Upload Date:** December 16, 2025
**Source:** [YouTube](https://www.youtube.com/watch?v=tFqMpi7KuzI)

## Summary
This tutorial demonstrates how to build a modern, cinematic personal website with smooth animations and parallax effects using only Google's free AI tools—no coding required. The workflow combines visual AI tools (Whisk, Nano Banana, Flow) with Firebase Studio to create professional websites that previously required design and development teams.

**Key Value Proposition:** What used to take weeks of design, coding, and trial and error can now be built in hours with a clear, repeatable workflow.

## Tools Used
1. **Nano Banana** - Establishes visual style and brand identity
2. **Google Whisk** - Generates opening and closing frames (first/last visual bookends)
3. **Google Flow (Veo 3.1)** - Creates smooth animations between frames
4. **Ezgif** - Converts video to WebP frame sequences
5. **Supabase** - Hosts and stores WebP frame assets
6. **Firebase Studio** - Builds the actual website with layout and interactions

## The Complete Workflow

### Phase 1: Visual Identity & Frame Creation
**Goal:** Create the "first and last frames" that define your website's aesthetic

#### Step 1: Generate Opening Frame with Google Whisk
1. Open [Google Whisk](https://whisk.google.com)
2. Copy the **Starting Frame Nano Banana Prompt** (see Prompts section below)
3. Paste into Whisk's prompt box and hit Enter
4. Review the generated image for:
   - Spacing and composition
   - Lighting and color balance
   - Overall polished, modern aesthetic
5. Re-run if needed until satisfied
6. Download the first frame

#### Step 2: Generate Closing Frame
1. Repeat the same process with the **Ending Frame Prompt**
2. Download the last frame
3. **Result:** Two "bookend" images that define your visual arc from opening to closing

---

### Phase 2: Animation & Motion
**Goal:** Transform static frames into fluid, cinematic animation

#### Step 3: Animate Frames with Google Flow
1. Open [Google Flow](https://flow.google.com)
2. Switch from "Text to Video" to **"Frames to Video"** mode
3. Upload both frames:
   - Starting frame (first)
   - Ending frame (last)
4. Copy the **Flow Animation Prompt** (see Prompts section)
5. Paste into prompt box and hit Enter
6. Wait for Flow to generate the animation using Veo 3.1
7. Review the motion for:
   - Smooth transitions
   - Balanced spacing
   - Premium minimal feel
8. Download the animation video

---

### Phase 3: WebP Conversion
**Goal:** Convert animation into web-optimized frame sequence

#### Step 4: Convert to WebP Sequence with Ezgif
1. Go to [Ezgif.com](https://ezgif.com)
2. Select **"Video to WebP"**
3. Upload the Flow animation video
4. Configure settings:
   - **Resolution:** Original (keeps visuals sharp)
   - **FPS:** Select closest native FPS shown
   - **Quality:** 85 (balance between quality and file size)
5. Click **Convert**
6. Once processed, click **Split** to break WebP into individual frames
7. Download the ZIP file containing all frames

**Note:** Quality may drop slightly—you can upscale later if needed, but focus on the workflow first.

---

### Phase 4: Asset Storage
**Goal:** Upload frames to a database that your website can access

#### Step 5: Upload to Supabase Storage
1. Go to [Supabase](https://supabase.com) and create account if needed
2. Create a new project and fill out the form
3. In left dashboard, click **Storage**
4. Create a new **Bucket** (think of it as an organized folder)
   - Give it a recognizable name
   - Set to **Public** (so website can access)
5. Upload the WebP frame sequence ZIP
6. **Copy the URL** of the first frame—you'll need this for Firebase

---

### Phase 5: Website Build
**Goal:** Assemble everything into a functional website

#### Step 6: Build Site with Firebase Studio
1. Open [Firebase Studio](https://firebase.google.com/products/app-hosting)
2. Copy the **Website Layout Prompt** (see Prompts section)
3. Paste into Firebase Studio's prompt box
4. In the prompt, replace the placeholder with:
   - The Supabase URL of your first WebP frame
   - This ensures visual consistency throughout the build
5. Hit Enter and let Firebase analyze the prompt
6. Click **"Prototype This"** to generate the first layout version
7. Preview the website—check:
   - Clean layout structure
   - Spacing and balance
   - Modern aesthetic alignment
8. Run refinement prompts to polish:
   - Tighten spacing
   - Improve visual balance
   - Ensure smooth scroll behavior

**Result:** A polished personal website with minimalistic, modern design and visual consistency.

---

### Phase 6: Export & Deploy
**Goal:** Get your website code and deploy to custom domain

#### Step 7: Export Code from Firebase
1. In Firebase project, click **"Switch to Code Editor"**
2. Select all files (Ctrl+A or Cmd+A)
3. Right-click → Select **"Zip and Download"**
4. Your codebase is now exported and ready for deployment

#### Step 8: Deploy to Custom Domain
1. Upload exported code to your hosting provider (Vercel, Netlify, etc.)
2. Connect your custom domain
3. Wait 24 hours for DNS propagation
4. Your website is now live!

---

## Prompts Referenced

The video references a "prompt document" available in Andy's free community. While exact prompts aren't shown on screen, the video describes their purpose:

### 1. Starting Frame Nano Banana Prompt
**Purpose:** Generate the opening visual with polished, modern aesthetic
**Key Elements:**
- Defines spacing and composition
- Sets lighting and color balance
- Establishes "cinematic" and "intentional" feel
- Creates clean, modern look

### 2. Ending Frame Prompt
**Purpose:** Generate the closing visual that bookends the site
**Key Elements:**
- Matches aesthetic of starting frame
- Provides visual closure
- Maintains cohesive brand feel

### 3. Flow Animation Prompt
**Purpose:** Instruct Flow how to animate between frames
**Key Elements:**
- Preserves clean, modern look
- Creates smooth transitions
- Maintains balanced spacing
- Generates premium minimal feeling
- Enables parallax-ready movement

### 4. Website Layout Prompt
**Purpose:** Define the structure and aesthetic for Firebase Studio
**Key Elements:**
- Sets spacing and structure
- Defines modern aesthetic direction
- Includes Supabase WebP frame URL
- Establishes scroll behavior
- Creates interactive sections
- Ensures visual consistency with generated frames

**Note:** Full prompts are available in Andy's free Skool community (link in video description).

---

## Key Insights

### Why This Workflow Works
1. **Visual-First Approach:** Start with aesthetics, not code
2. **AI-Powered Motion:** Flow handles complex animations automatically
3. **Frame-Based Animation:** WebP sequences enable smooth scroll-triggered effects
4. **No-Code Assembly:** Firebase Studio handles the technical implementation
5. **Modular System:** Each tool has one clear job in the pipeline

### What Makes Sites Built This Way "Premium"
- **Cinematic feel** from intentional frame composition
- **Smooth parallax** from frame-by-frame control
- **Consistent brand** through Nano Banana visual identity
- **Interactive moments** that feel handcrafted, not templated
- **Professional polish** without needing design/dev teams

### Workflow Advantages
- ✅ Repeatable process for multiple sites
- ✅ No deep technical skills required
- ✅ All tools are free (Google AI ecosystem)
- ✅ Export code for hosting anywhere
- ✅ Fast iteration (hours vs. weeks)

---

## Technical Details

### Why WebP Frame Sequences?
- Lightweight for browsers
- Scroll-triggered animation support
- Better quality than GIF
- Frame-by-frame control for parallax

### Supabase vs. Other Storage
- Easy public bucket setup
- Direct URL access for each frame
- Free tier sufficient for personal sites
- Simple integration with Firebase

### Firebase Studio Capabilities
- Analyzes natural language prompts
- Generates layout and structure automatically
- Handles scroll behavior and interactions
- Exports clean, deployable code
- Iterative refinement through prompting

---

## Resources

**Official Links (from video description):**
- AI Website Design Early Access: https://s.andynocode.com/ai-design-youtube-20251216
- Free AI Community (prompts available): https://www.skool.com/andynocode
- n8n 14-day trial: https://n8n.partnerlinks.io/dx7m59h2279k
- Apify 30% OFF: https://www.apify.com?fpr=c5kjv

**Tools Used:**
- Google Whisk: https://whisk.google.com
- Google Flow: https://flow.google.com
- Ezgif: https://ezgif.com
- Supabase: https://supabase.com
- Firebase Studio: https://firebase.google.com/products/app-hosting

---

## Personal Notes

**Why This Matters for My Workflow:**
- Demonstrates how to create motion-rich websites without coding
- Workflow is applicable to landing pages, portfolios, and brand sites
- Free tools make this accessible for rapid prototyping
- Frame-based animation technique is transferable to other projects
- Shows how to combine multiple AI tools into a cohesive pipeline

**Potential Applications:**
- Personal portfolio site
- Project showcase pages
- Landing pages for side projects
- Client presentation demos
- Visual storytelling projects

---

## Timestamps
- 00:00 - Start
- 00:57 - Why Nano Banana is Good
- 02:06 - Design Workflow Introduction
- 03:59 - Tutorial Start
- 04:13 - Demo 1: Whisk (Frame Generation)
- 06:04 - Demo 2: Google Flow (Animation)
- 07:27 - Demo 3: Ezgif (WebP Conversion)
- 09:10 - Demo 4: Supabase (Asset Storage)
- 10:10 - Demo 5: Firebase Studio (Website Build)
- 12:53 - Conclusion & Export Guide

---

## Related Concepts
- **Parallax scrolling** - Visual effect where background moves slower than foreground
- **Micro-interactions** - Small animated responses to user actions
- **Cinematic design** - Film-inspired aesthetic with intentional framing and motion
- **No-code development** - Building software without traditional programming
- **Visual identity system** - Cohesive aesthetic across all brand touchpoints
