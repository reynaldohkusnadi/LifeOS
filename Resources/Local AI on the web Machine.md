---
type: Video
source: YouTube
url: https://www.youtube.com/watch?v=2QpXab8z_Gw
author: Alex Ziskind
duration: 14 minutes
created: 2025-12-10
status: Active
area: "[[AI]]"
tags:
  - ai
  - local-ai
  - hardware
  - ollama
  - comfy-ui
  - nvidia
  - self-hosted
---

# Local AI on the web Machine

## Summary

Alex Ziskind reviews the **Olares One**, a purpose-built personal AI appliance that reimagines how we interact with local AI. Unlike generic PCs with AI capabilities bolted on, this device is designed as a headless server you can access from anywhere—your desktop, phone, or iPad—without complex network configuration.

## Key Takeaways

1. **Purpose-Built AI Appliance**: Not meant to be used with keyboard/mouse/monitor directly. Instead, it's a personal cloud server accessible via secure web interface from any device, anywhere.

2. **Impressive Specs**:
   - Intel Core Ultra 9 275HX processor
   - Nvidia RTX 5090 mobile GPU (24GB VRAM)
   - 96GB system RAM
   - 2TB SSD storage
   - Thunderbolt 5 connectivity

3. **Zero-Config Remote Access**: Built-in VPN, free HTTPS certificates, and multi-factor authentication—no need to configure firewalls or set up Tailscale manually.

4. **App Marketplace**: One-click installation for AI tools:
   - **Ollama** - LLM inference
   - **Open WebUI** - Chat interface (auto-detects installed models)
   - **Comfy UI** - Image/video generation with workflow packages
   - **Aceep** - Music generation
   - Plus home server apps like Jellyfin, Home Assistant, N8N

5. **Performance**: The RTX 5090's GDDR7 memory delivers exceptional speed—Qwen 3 30B runs noticeably faster than competitors including Mac Studio M3 Ultra and Nvidia DGX Spark.

6. **Limitations**: 24GB VRAM means larger models (120B+) must offload to CPU/system RAM, slowing inference compared to machines with 96GB+ unified memory.

7. **GPU Sharing Modes**: Three options for multi-app GPU usage:
   - App Exclusive (dedicated)
   - Memory Slicing (divide VRAM)
   - Time Slicing (apps take turns)

## Why It Matters

This represents a shift from trading ownership for convenience. Instead of sending data to cloud providers, you can run your own models, files, and AI agents on hardware you own—while still accessing them from anywhere like a cloud service.

## Practical Applications

- Run coding assistants (Qwen Coder 30B) locally with privacy
- Generate images/videos without cloud API costs
- Create a personal media server alongside AI tools
- Access your AI stack from coffee shops without slow model downloads
- Keep client data private while still using powerful AI

## Price Point

~$3,000 on Kickstarter—expensive but includes latest-gen components (5090 GPU, Thunderbolt 5) not available in other mini PCs.

---

**Related**: [[AI]], Local LLMs, Self-Hosted AI
