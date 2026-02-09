# 01 Platform Trade-offs

## Purpose
Capture platform choice trade-offs for authentication, data, hosting, and billing integration for Jinshu.

## Decision Context
- Product type: text-to-picture tool (no AI generation in v1).
- Cost goal: near-zero fixed cost when user count is low.
- Business goal: simple subscription flow for global users and Mainland China users.
- Constraint: no local China cloud provider for now.
- Constraint: no ICP filing in current phase.

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
- Mainland China access path is cross-border in this phase (latency variability risk).

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
- Stripe-only subscription UX can be weak for some Mainland China users.

Best fit:
- Small products optimizing for low burn, predictable cost, and fast iteration.

### Option C: Full Cloudflare (Pages + Workers + D1 + Stripe)
Pros:
- Low fixed cost and strong edge performance.
- Consolidated hosting/runtime/database within one platform.

Cons:
- More custom backend/auth work than managed auth platforms.
- Higher engineering effort for account and entitlement management.
- Same payment and cross-border access risks if Stripe is the only billing path.

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
- For Mainland China users, Stripe-only may not deliver the easiest recurring subscription experience.
- Keep provider abstraction in billing domain so another payment provider can be added without rewriting entitlement logic.

## Mainland China Strategy (No ICP Now)
Assumptions:
- Product stays on global hosting in this phase.
- No local China cloud provider is introduced.
- No ICP filing is started yet.

Network strategy:
- Use APAC region placement where possible (for example Hong Kong, Singapore, or Tokyo) to reduce median latency.
- Treat Mainland access as cross-border and design for degraded network conditions (retry, timeout, resumable flows).
- Keep static assets aggressively cached and minimize first-load bundle size.

Subscription strategy:
- Do not couple subscription lifecycle to one PSP API surface.
- Keep `billing_customer`, `billing_subscription`, and `billing_entitlement` as provider-agnostic tables.
- Implement provider adapters:
  - Adapter 1: Stripe (cards and existing global flow).
  - Adapter 2: alternate provider with better China-friendly checkout for recurring subscriptions.
- Use a single entitlement projector fed by normalized webhook events.

Data model baseline:
- `billing_provider` (enum/string): source of truth for each customer subscription.
- `provider_customer_id`, `provider_subscription_id`: provider-native references.
- `plan_id`, `status`, `current_period_end`, `cancel_at_period_end`.
- `entitlement_state` derived from subscription status, not from frontend callback.

Operational rule:
- Launch with cross-border hosting and multi-provider billing before ICP.
- Start ICP evaluation only when Mainland conversion impact justifies compliance and ops overhead.

## Recommended Baseline for v1
Recommendation: **Option B (Supabase + Cloudflare + provider-abstracted billing)**.

Why:
- Best match for "small and beautiful" product economics.
- Low fixed cost while user base is small.
- Good enough backend capability without overbuilding.
- Compatible with "no local cloud / no ICP now" while still improving China subscription conversion.
- Reduces lock-in risk by separating entitlement logic from any single payment provider.

## Re-evaluation Triggers
- Need very deep Google ecosystem integration.
- MAU and backend workloads exceed free/low tiers.
- Team decides to consolidate vendors for operational simplicity.
- Mainland conversion remains blocked after multi-provider checkout rollout.
- Business is ready to handle ICP and China in-country delivery operations.

## Status
- Initial baseline recorded: 2026-02-08
- Updated for China access and subscription constraints: 2026-02-09
- Owner: Product + Engineering
