# 07 Decision Log

## Purpose

Record product decisions with timestamp and rationale to keep a stable decision context for AI and collaborators.

## Status Legend

- `Proposed`: drafted, not yet approved.
- `Approved`: confirmed baseline.
- `Deprecated`: replaced by a newer decision.

## Entries

| Decision ID | Date       | Topic                | Decision                                                                                   | Status   | Owner   | Rationale                                                                     |
| ----------- | ---------- | -------------------- | ------------------------------------------------------------------------------------------ | -------- | ------- | ----------------------------------------------------------------------------- |
| `DEC-001`   | 2026-02-08 | Content policy       | v1 excludes AI text generation and rewriting features.                                     | Approved | Product | Preserve product positioning around human-authored, high-substance content.   |
| `DEC-002`   | 2026-02-08 | MVP workflow         | v1 scope is strictly `write -> template -> preview -> export`.                             | Approved | Product | Keep validation path short and reduce implementation risk.                    |
| `DEC-003`   | 2026-02-08 | Platform support     | v1 includes default presets for Xiaohongshu, X, Instagram.                                 | Approved | Product | Multi-platform output is a direct user need and conversion driver.            |
| `DEC-004`   | 2026-02-08 | Pricing stage        | v1 can use lightweight paid entry (`9 RMB/month`), while `19/29` Pro tiers start in v1.1+. | Approved | Product | Prioritize activation before complex tier management.                         |
| `DEC-005`   | 2026-02-08 | Live Photo timing    | Live Photo is a v1.1 experimental feature, not part of v1 mainline.                        | Approved | Product | Good differentiator but not core value proof for MVP.                         |
| `DEC-006`   | 2026-02-08 | LaTeX timing         | Full LaTeX support is not in v1/v1.1 and is demand-gated for v2+.                          | Approved | Product | Avoid early complexity before core workflow metrics stabilize.                |
| `DEC-007`   | 2026-02-08 | Template strategy    | v1 launches with 8 high-quality templates, not large-volume template catalog.              | Approved | Product | Quality and consistency beat quantity for early retention.                    |
| `DEC-008`   | 2026-02-08 | Persistence strategy | v1 uses local autosave by default; cloud history requires login in v1.1.                   | Approved | Product | Lower friction for first-time use while reserving account value for upgrades. |

## Update Rules

- Add a new row for each decision change; do not overwrite historical rows.
- If a decision is replaced, mark old row as `Deprecated` and reference the new `Decision ID` in commit message.
- Product decisions must be reflected in:
  - `04-scope-matrix.md`
  - `05-prd-v0.md`
