# 04 Scope Matrix - Jinshu

## Purpose

Provide a single source of truth for what is in scope per release.

## Status Legend

- `MUST`: committed for that release.
- `SHOULD`: likely for that release if capacity allows.
- `NO`: explicitly not included.

## Capability Matrix

| Capability ID | Capability                                            | v1     | v1.1   | v1.2+  | Notes                                 |
| ------------- | ----------------------------------------------------- | ------ | ------ | ------ | ------------------------------------- |
| `CAP-001`     | Human-authored text input                             | MUST   | MUST   | MUST   | No AI writing entry point             |
| `CAP-002`     | Basic Markdown support                                | MUST   | MUST   | MUST   | Headings, paragraphs, lists, emphasis |
| `CAP-003`     | AI text generation/rewriting                          | NO     | NO     | SHOULD | Only revisit after core validation    |
| `CAP-004`     | Real-time paginated preview                           | MUST   | MUST   | MUST   | Core value driver                     |
| `CAP-005`     | Platform presets (XHS/X/Instagram)                    | MUST   | MUST   | MUST   | One-click aspect ratio switch         |
| `CAP-006`     | Launch template set (8 quality templates)             | MUST   | MUST   | MUST   | Quality over quantity                 |
| `CAP-007`     | PNG export (single/all pages)                         | MUST   | MUST   | MUST   | Preview-export consistency required   |
| `CAP-008`     | Local autosave and reopen                             | MUST   | MUST   | MUST   | Reduces onboarding friction           |
| `CAP-009`     | Cloud history and sync                                | NO     | MUST   | MUST   | Requires login                        |
| `CAP-010`     | Free tier limits (`5/day`, `20 pages`, `3 templates`) | MUST   | MUST   | MUST   | Cost control baseline                 |
| `CAP-011`     | Lightweight paid tier (`9 RMB/month`)                 | SHOULD | MUST   | MUST   | Keep simple in v1                     |
| `CAP-012`     | Pro tiers (`19/29`)                                   | NO     | SHOULD | MUST   | Premium templates and brand controls  |
| `CAP-013`     | Live Photo support                                    | NO     | SHOULD | SHOULD | Experimental in v1.1                  |
| `CAP-014`     | Full LaTeX support                                    | NO     | NO     | SHOULD | Demand-gated roadmap item             |
| `CAP-015`     | Analytics baseline events                             | MUST   | MUST   | MUST   | Activation and export funnel          |

## Release Gates

Move from `v1` to `v1.1` only when:

- Activation rate >= 40%.
- Export success rate >= 98%.
- 7-day return rate >= 20%.
- Mainline flow support tickets are under control.

## Change Control

- Any scope change must update this file first.
- Each changed row must include a short rationale in commit message.
