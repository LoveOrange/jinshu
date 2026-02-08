# 4-Week Launch Roadmap - Jinshu

## Goal
Publish a working MVP to real users within 4 weeks, then iterate from feedback.

## Week 1 - Definition + Foundations
### Deliverables
- Finalize product vision and MVP scope.
- Finalize PRD v0 and architecture decisions.
- Set up repository, environments, CI, and basic deployment pipeline.
- Create low-fidelity UI flow for editor, preview, and export.

### AI Leverage
- Generate requirement drafts and edge-case lists.
- Generate architecture decision records (ADRs).
- Produce initial component stubs and task breakdown.

### Exit Criteria
- Scope freeze for v1.
- Engineering backlog with priorities and acceptance criteria.
- Preview skeleton running in browser.

## Week 2 - Core Build (Editor + Render + Templates)
### Deliverables
- Markdown editor with basic syntax handling.
- Live paginated preview rendering.
- First 3 templates implemented.
- Basic project save/load implemented.

### AI Leverage
- Speed up component implementation and refactoring.
- Generate tests for parser, pagination, and template rendering.
- Assist with performance debugging.

### Exit Criteria
- End-to-end flow works internally: write -> preview -> switch template.
- Core quality targets roughly met in local profiling.

## Week 3 - Export + Beta Readiness
### Deliverables
- PNG export (single/all pages).
- Remaining templates (up to 5-10 total).
- Error handling + analytics events.
- Beta onboarding and landing page draft.

### AI Leverage
- Generate instrumentation plans and SQL/dashboard queries.
- Draft onboarding and launch copy.
- Find likely failure points from logs and traces.

### Exit Criteria
- Stable private beta build.
- 5-10 pilot users onboarded.
- Feedback collection loop active.

## Week 4 - Publish + Iterate
### Deliverables
- Public launch deployment.
- Optional free-tier limit + payment integration (or soft paywall placeholder).
- Performance/stability fixes from beta feedback.
- Publish launch materials (website copy, social announcement, FAQ).

### AI Leverage
- Summarize user feedback and prioritize fixes.
- Draft pricing experiment options.
- Generate release notes/changelog.

### Exit Criteria
- Public product is live.
- First real usage data available.
- Post-launch 2-week iteration backlog prioritized.

## Operating Cadence (Weekly)
- Monday: define outcomes and top 3 priorities.
- Mid-week: ship at least one user-visible increment.
- Friday: review metrics, feedback, and reprioritize.

## KPI Dashboard (Initial)
- Signups
- Activation rate (first export)
- Exports per active user
- 7-day return rate
- Upgrade click-through rate
- Export failure rate

## Risk Controls
- Keep scope tight: no major new features after Week 1 freeze.
- Maintain fallback export path for edge cases.
- Define visual quality baseline for templates before launch.

## Post-Launch (Next 2-4 Weeks)
- Improve top 2 templates based on usage.
- Add advanced formatting and possibly LaTeX as v1.1.
- Run pricing and free-limit experiments.
- Build repeatable content creator onboarding.
