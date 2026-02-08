# 01 Platform Trade-offs

## Purpose
Capture platform choice trade-offs for authentication, data, hosting, and billing integration for Jinshu.

## Decision Context
- Product type: text-to-picture tool (no AI generation in v1).
- Cost goal: near-zero fixed cost when user count is low.
- Business goal: simple subscription flow with Stripe.

## Options Compared

### Option A: Firebase (Hosting + Auth + Firestore + Functions)
Pros:
- Fast end-to-end setup from one vendor.
- Strong developer ecosystem and documentation.
- Easy path to add Google ecosystem features later.

Cons:
- Stripe production integration usually requires Functions deploy on Blaze.
- Cost predictability can be weaker once usage grows across multiple Firebase services.
- Some services have free-tier constraints that become operational constraints at scale.

Best fit:
- Teams that prefer tight Google platform integration and can accept Blaze billing model.

### Option B: Supabase + Cloudflare (Pages + optional Workers) + Stripe
Pros:
- Very low fixed cost at early stage.
- Clear and predictable pricing surfaces.
- Good SQL-first data model and straightforward auth.
- Works well for local-first frontend with lightweight backend.

Cons:
- Multi-vendor setup (Supabase + Cloudflare + Stripe) adds integration overhead.
- Requires discipline in auth/session and webhook design.

Best fit:
- Small products optimizing for low burn, predictable cost, and fast iteration.

### Option C: Full Cloudflare (Pages + Workers + D1 + Stripe)
Pros:
- Low fixed cost and strong edge performance.
- Consolidated hosting/runtime/database within one platform.

Cons:
- More custom backend/auth work than managed auth platforms.
- Higher engineering effort for account and entitlement management.

Best fit:
- Teams comfortable building more backend primitives themselves.

## Cost Behavior by User Scale (Infra Only, Excluding Stripe Fees)
Assumptions:
- Mostly client-side rendering/export.
- Light backend usage.
- Auth method excludes SMS-heavy flows.

| Scale (MAU) | Firebase (base auth path) | Supabase + Cloudflare | Notes |
|---|---:|---:|---|
| 100 | ~0 USD | ~0 USD | Both fit free tier |
| 1,000 | ~0 USD | ~0 USD | Both fit free tier |
| 10,000 | low (near free with light usage) | ~0 USD | Supabase + Cloudflare remains near-zero |
| 50,000 | low-to-moderate | ~0 USD | Watch Supabase free limits and function usage |
| 100,000 | moderate to high (depends on services used) | ~25 USD baseline (Supabase Pro) | Supabase pricing more predictable here |

## Stripe Integration Considerations
- Both Firebase and Supabase paths can support Stripe Checkout + webhook entitlement sync.
- Minimum safe architecture requires:
  - secure webhook endpoint
  - subscription status table
  - idempotent event handling

## Recommended Baseline for v1
Recommendation: **Option B (Supabase + Cloudflare + Stripe)**.

Why:
- Best match for "small and beautiful" product economics.
- Low fixed cost while user base is small.
- Good enough backend capability without overbuilding.

## Re-evaluation Triggers
- Need very deep Google ecosystem integration.
- MAU and backend workloads exceed free/low tiers.
- Team decides to consolidate vendors for operational simplicity.

## Status
- Initial baseline recorded: 2026-02-08
- Owner: Product + Engineering
