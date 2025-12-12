---
type: resource
category: Video
resource-type: YouTube Video
url: https://www.youtube.com/watch?v=zM9k0WI1FrM
rating: 0
date-added: 2025-12-10
date-consumed:
author:
tags:
  - resource
  - business
  - payments
  - stripe
  - polar
  - saas
  - video
  - tutorial
status: To Watch
area: "[[Big Beautiful Business Idea]]"
related-to: []
created: 2025-12-10
modified: 2025-12-10
---

# Why I'm No Longer Using Stripe - Polar.sh as MOR

## Resource Information
- **Type:** YouTube Video
- **Category:** Video
- **URL:** https://www.youtube.com/watch?v=zM9k0WI1FrM
- **Author:** Unknown (Developer YouTuber)
- **Rating:** (0/5)
- **Status:** To Watch
- **Date Added:** 2025-12-10

## Summary
A developer explains why they migrated from Stripe to Polar.sh for payment processing. The key issue with Stripe is that while it handles payment processing and tax collection, it doesn't handle tax remittance (reporting and paying taxes to authorities). Polar.sh is a "Merchant of Record" (MOR) that acts as the legal seller, handling all tax compliance automatically for a 4% fee.

## Key Takeaways
1. **Stripe's limitation**: Stripe collects taxes but doesn't remit them - you must register with tax authorities and file quarterly reports yourself, which is time-consuming and error-prone
2. **Merchant of Record (MOR)**: Services like Polar.sh, Lemon Squeezy, and Paddle act as the legal seller, handling all tax compliance, refunds, and disputes for you
3. **Polar.sh is the cheapest MOR** at 4% fee (vs Stripe's 2.9% + your tax compliance work), with easy onboarding and great developer experience
4. **Trade-off**: MORs may charge customers more tax (since they've exceeded thresholds in more jurisdictions), but saves significant time on compliance
5. **Works globally**: Because Polar.sh is the merchant of record, it handles international sales tax - making it viable for developers in countries where Stripe is limited (like Indonesia)

## Highlights & Notes

### Important Points
- EU/UK requires tax remittance from first sale (no threshold) - very complex for indie developers
- Stripe's Tax Complete service ($90-430/month) is limited and still requires manual work
- Polar.sh features: Discord invites, GitHub repo access, file downloads as "benefits"
- Migration from Stripe to Polar is straightforward - similar concepts (products, customers, webhooks)

### Key Differences: Stripe vs Polar
| Aspect | Stripe | Polar.sh |
|--------|--------|----------|
| Product/Price | One product, multiple prices | One product = one price |
| Customer ID | Need lookup table | Can use external_id (your user ID) |
| ID format | Prefixed object IDs | UUIDs |
| Tax handling | Collection only | Full remittance |
| Fee | 2.9% | 4% |

### Quotes
> "I would rather spend my time both building and creating... So I decided to outsource this and migrate over to another solution that would allow me to buy back some time."

> "Polar describes themselves as the cheapest Merchant of Record on the market."

### Personal Insights
This is highly relevant for building SaaS products targeting global customers, especially from Indonesia where Stripe has limitations. Polar.sh handles the complexity of international tax compliance, letting you focus on building.

## How to Apply
- Use Polar.sh for any new SaaS products to avoid tax compliance headaches
- Consider migration if current Stripe setup is causing tax compliance issues
- Check Polar.sh sandbox environment (sandbox.polar.sh) for testing
- Look into BetterAuth plugin for quick Polar integration

## Related Resources
- Polar.sh documentation
- BetterAuth integration guide

## Tags & Categories
**Topics:** Payments, SaaS, Tax Compliance, Merchant of Record, Developer Tools
**Area:** `= this.area`
**Projects Related:**

## Review

**Would I recommend this?** Yes

**Who would benefit from this?** Indie developers, SaaS builders, anyone selling digital products globally, developers in countries with limited Stripe support (like Indonesia)

**When to revisit:** When starting a new SaaS project or dealing with tax compliance issues

---
*Resource added: 2025-12-10*
