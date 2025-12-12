---
type: video
status: Active
source: youtube
url: https://www.youtube.com/watch?v=ELkPcuO5ebo
author: Dreams of Code
duration: 25 minutes
created: 2025-12-10
area: "[[Big Beautiful Business Idea]]"
tags:
  - devops
  - deployment
  - self-hosting
  - vps
  - docker
  - paas
---

# Dokploy - Vercel Replacement to Host Applications Using Hostinger VPS

## Summary

Dokploy is a self-hosted Platform as a Service (PaaS) that provides Vercel-like deployment features on your own VPS. The creator demonstrates how to set up Dokploy on a Hostinger VPS and deploy a Next.js application with automated deployments and preview environments.

## Key Takeaways

### Why Dokploy?
- **Best UI among self-hosted PaaS options** - Comparable to Vercel's interface
- **Free and self-hosted** - Only cost is your VPS
- **Review/Preview Apps** - Critical for agentic AI workflows where you need to review AI-generated code changes
- **Full feature set** including automated deployments, monitoring, HTTPS, and secrets management

### Features
- Automated deployments on git push
- Application and server monitoring
- Automatic HTTPS via Let's Encrypt
- Secrets/environment variable management
- Preview deployments for pull requests
- Docker Compose support
- Built-in database deployments (Postgres, MongoDB, MySQL, Redis)
- Multiple build options: Dockerfile, Nixpacks, Railpack

### Setup Process
1. **Get a VPS** - Ubuntu LTS recommended (24.04)
2. **Install Dokploy** - Single CLI command from dokploy.com
3. **Configure HTTPS** - Add domain, enable Let's Encrypt
4. **Connect GitHub** - Create GitHub App for repo access
5. **Deploy services** - Create projects, add databases and applications
6. **Enable preview deployments** - Configure wildcard domain for review apps

### Hostinger VPS Recommendation
- **KVM2 Plan**: 2 vCPUs, 8GB RAM at $6.99/month (24-month term)
- 100GB storage - enough for self-hosted Postgres
- Pre-built Dokploy image available

### Technical Notes
- Build on the same box isn't ideal for production (impacts performance)
- Can use CI/CD pipeline for builds instead
- Internal database URLs available for service-to-service communication
- Environment variables available at both build and runtime

## Compared to Alternatives
- **Coolify** - Tested but found underwhelming
- **Vercel/Railway/Netlify** - Great but not self-hosted
- **Docker Stack** - Works but lacks preview deployments

## Resources
- Dokploy: https://dokploy.com
- Dokploy Cloud (managed option): Available on their website
- Hostinger: https://hostinger.com/dreamsofcode (coupon: DREAMSOFCODE for 10% off)
- Demo Guestbook Source: https://github.com/dreamsofcode-io/guestbook-v2

## When to Use
- You want Vercel-like features but self-hosted
- You need preview/review apps for PR workflows
- You're working with agentic AI and need to review generated code
- You want to consolidate multiple services on one VPS
- You prefer local-first control over your infrastructure
