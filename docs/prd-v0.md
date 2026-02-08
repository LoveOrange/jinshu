# PRD v0 - Jinshu

## 1. Objective
Build and publish an MVP web product that converts Markdown articles into Xiaohongshu-style full-screen image posts with live preview and export.

## 2. Non-Goals
- Build a full Notion-like editor.
- Build a full typography/layout design suite.
- Support every input format in v1.

## 3. Core User Story
As a creator, I can paste or write Markdown content, choose a template, preview pages in real time, and export a polished image set for posting.

## 4. Functional Requirements

### 4.1 Content Input
- Markdown text input area.
- Basic syntax support for:
  - headings
  - paragraphs
  - lists
  - bold/italic
  - quote/code blocks (basic)
- Character and page count indicator.

### 4.2 Live Preview
- Render content into paginated cards/images.
- Switch template and update preview instantly.
- Preview in mobile/full-screen aspect ratio mode.

### 4.3 Templates
- Include 5-10 templates for launch.
- Template controls include at least:
  - font family
  - font size scale
  - color theme
  - spacing preset
- Templates must preserve readability and branding consistency.

### 4.4 Export
- Export single page or all pages as PNG.
- Export resolution options (at least one default mobile-optimized size).
- Export operation should complete within 10 seconds for normal-length posts (target <= 20 pages).

### 4.5 Project Persistence
- Save project locally (or account-based if auth is enabled).
- Re-open and continue editing previous project.

### 4.6 Usage Limits (Monetization Foundation)
- Free tier limit (e.g., exports per day/month).
- Placeholders for premium feature gating in UI.

## 5. Quality Requirements
- First contentful paint target: <= 2.5s on standard broadband.
- Editor-to-preview update latency target: <= 300ms for typical inputs.
- Error rate for export: < 2% in beta.
- Responsive support: desktop and mobile web.

## 6. UX Requirements
- Clean split layout:
  - left: editor
  - right: live preview
- Fast template switching (one click).
- Obvious export entry point.
- New-user onboarding: 3-step hint flow max.

## 7. Analytics Events (Minimum)
- `project_created`
- `markdown_edited`
- `template_selected`
- `export_clicked`
- `export_succeeded`
- `export_failed`
- `paywall_viewed`
- `upgrade_clicked`

## 8. MVP Tech Direction (Proposed)
- Frontend: React + TypeScript.
- Rendering: Markdown parser + custom pagination engine.
- Export: canvas/html-to-image pipeline.
- Backend (lightweight): auth + usage tracking + subscription state.

## 9. Acceptance Criteria
- A new user can complete: create -> preview -> export in first session without support.
- At least 1 stable template produces publish-ready output for long (10+ page) content.
- Exported images match preview within acceptable visual tolerance.

## 10. Launch Readiness Checklist
- Domain + SSL configured.
- Legal pages: Terms, Privacy.
- Support channel available (email or form).
- Basic observability: error monitoring + analytics dashboard.
- Payment flow tested end-to-end (if enabled at launch).

## 11. Open Questions
- Final free-tier limit policy?
- Should LaTeX be v1.1 or v2?
- Auth at launch or anonymous-first with optional account?
- Which 5-10 template styles map best to creator segments?
