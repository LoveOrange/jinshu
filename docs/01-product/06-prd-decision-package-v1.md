# PRD Decision Package v1 (Sign-off)

## Purpose

Convert the 4 unresolved PRD questions into sign-off decisions so build and launch can proceed without ambiguity.

## Decision Summary

| Decision            | Proposed Sign-off                                                                   | Why Now                                                    |
| ------------------- | ----------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Free-tier limit     | `5` full exports/day/device, max `20` pages/export, `3` free templates              | Protect export cost while preserving first-session success |
| LaTeX version       | Exclude from `v1` and `v1.1`; evaluate for `v2` after demand validation             | Keeps MVP focused and reduces rendering complexity risk    |
| Auth strategy       | Anonymous-first launch; login only required for cloud save/history and subscription | Fastest path to activation and lower onboarding friction   |
| Launch template set | Launch with `8` templates across core creator scenarios                             | Enough variety for validation without overbuilding         |

## 1) Free-tier Limit (Monetization Baseline)

### Proposed Sign-off

- Anonymous and free users:
  - `5` exports/day/device
  - up to `20` pages/export
  - access to `3` base templates
- Pro users:
  - higher or unlimited exports
  - premium template access

### Rationale

- Supports the MVP metric of quick first success.
- Avoids unlimited-cost abuse in image export.
- Creates a clear upgrade path without blocking trial value.

### Revisit Trigger

- Activation below `35%` after 2 weeks of public launch.
- Abuse-related export cost exceeds planned budget.

## 2) LaTeX Version Decision

### Proposed Sign-off

- No native LaTeX in `v1` and `v1.1`.
- Put LaTeX into `v2` candidate scope.

### Rationale

- Current core user promise is fast text-to-image publishing.
- LaTeX layout/rendering adds significant complexity and QA surface.
- Better to validate demand before committing roadmap capacity.

### Revisit Trigger

- `>=15%` of activated users attempt math-like syntax.
- `>=20%` of interview/beta feedback explicitly requests LaTeX.

## 3) Auth Strategy at Launch

### Proposed Sign-off

- Anonymous-first by default.
- Login required only for:
  - cloud save/history
  - subscription purchase and entitlement restore

### Rationale

- Reduces onboarding friction and improves first-session conversion.
- Keeps backend/auth complexity low for v1 launch speed.
- Still supports monetization and data continuity for paying users.

### Revisit Trigger

- Abuse from anonymous usage materially impacts cost/stability.
- Significant user demand for cross-device sync in free tier.

## 4) Launch Template Types (8)

### Proposed Sign-off

- `Template 01` Minimal Notes: clean educational text posts.
- `Template 02` Step-by-Step: tutorial/process style.
- `Template 03` Bold Opinion: headline-first观点表达.
- `Template 04` Quote Story: quote + narrative sections.
- `Template 05` List Cards: listicle and collection posts.
- `Template 06` Data Snapshot: numbers/facts with emphasis blocks.
- `Template 07` Soft Lifestyle: warm visual tone for lifestyle content.
- `Template 08` Personal Brand: creator profile and recurring series style.

### Rationale

- Covers major creator intents without over-expanding scope.
- Allows fast template usage validation by segment.

### Revisit Trigger

- Remove or replace templates with low adoption after 2 weeks.
- Add next 2 templates based on top requested content genres.

## Sign-off Checklist

- Owner: Product
- Reviewer: Engineering + Design
- Target sign-off date: `2026-02-10`
- Rule: If not signed off by date, use this document as default MVP decision baseline and continue execution.
