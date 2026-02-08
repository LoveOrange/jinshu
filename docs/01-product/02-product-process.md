# Product Process - Idea to Published Product

## Purpose

Define a repeatable process to move from product idea to public launch, while maximizing AI leverage in design, engineering, and go-to-market.

## Phase 1 - Problem and Goal Framing

### Inputs

- Initial idea
- Target platform/context
- Suspected user pain

### Actions

- Define target user and top 3 pain points.
- Define product promise in one sentence.
- Define one primary success metric for MVP.

### Outputs

- Vision document
- MVP success metric
- Initial assumptions list

### AI Role

- Generate positioning variants.
- Stress-test assumptions and identify risk areas.

## Phase 2 - Validation

### Actions

- Run 5-10 user interviews with target creators.
- Test prototype or fake-door landing page.
- Validate willingness to adopt/pay.

### Outputs

- Validation summary
- Prioritized user needs
- Updated problem statement

### AI Role

- Generate interview scripts.
- Summarize transcripts and cluster themes.
- Suggest pricing hypothesis tests.

## Phase 3 - Scope and PRD

### Actions

- Freeze MVP scope.
- Define non-goals clearly.
- Convert requirements into measurable acceptance criteria.

### Outputs

- PRD v0
- Prioritized backlog
- Launch checklist draft

### AI Role

- Convert product requirements into testable stories.
- Identify edge cases and missing constraints.

## Phase 4 - UX/UI Design

### Actions

- Design core user flow.
- Define template system and visual standards.
- Build clickable prototype.

### Outputs

- UI flow and wireframes
- Template specs
- Design tokens (color/type/spacing)

### AI Role

- Generate layout options and copy variants.
- Critique readability and consistency.

## Phase 5 - Build MVP

### Actions

- Implement smallest vertical slice first.
- Iterate until full MVP flow works end-to-end.
- Add instrumentation and quality checks.

### Outputs

- Internal MVP build
- Basic analytics and error tracking
- Test coverage for critical paths

### AI Role

- Scaffold components and tests.
- Assist in refactoring/performance tuning.
- Generate technical docs and ADRs.

## Phase 6 - Beta and Stabilization

### Actions

- Onboard pilot users.
- Collect behavior + qualitative feedback.
- Fix top reliability and UX blockers.

### Outputs

- Beta feedback report
- Prioritized bug/UX fix list
- Launch decision

### AI Role

- Analyze feedback, propose priorities.
- Find root-cause patterns from logs.

## Phase 7 - Publish and Grow

### Actions

- Public launch.
- Enable monetization baseline (free limits + upgrade path).
- Run weekly iteration loop.

### Outputs

- Live product
- KPI dashboard
- Post-launch roadmap

### AI Role

- Draft launch copy and release notes.
- Generate weekly KPI summaries and experiment proposals.

## Working Rules for AI-Driven Execution

- Keep a single source of truth in `/docs`.
- For each task, define: goal, constraints, acceptance criteria, non-goals.
- Use short loops: spec -> build -> test -> review -> ship.
- Require measurable output per phase before moving forward.

## Suggested Document Set

- `01-vision.md`
- `02-product-process.md`
- `03-story-map.md`
- `04-scope-matrix.md`
- `05-prd-v0.md`
- `06-prd-decision-package-v1.md`
- `../04-release/01-launch-roadmap-4-weeks.md`
- later: `../02-architecture/01-architecture-overview.md`, `../04-release/02-launch-checklist.md`, `../04-release/03-pricing-experiments.md`
