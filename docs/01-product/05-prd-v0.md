# PRD v0 - Jinshu

## 1. Objective

Build and publish an MVP web product that converts user-authored text (Markdown-first) into social-ready full-screen image posts with live preview and export.

Core constraint:

- Human-authored content first.
- No AI text generation or AI rewriting in v1.

## 2. Product Principles

- Simplicity first: one clear workflow, minimal decisions for users.
- Quality over feature count: output quality is more important than editor complexity.
- WYSIWYG reliability: preview and exported images should be visually consistent.

## 3. Non-Goals (v1)

- Build a full Notion-like editor.
- Build a full typography/layout design suite.
- Add AI writing/rewriting features.
- Add full LaTeX support.
- Add team collaboration/workspace permissions.
- Add Live Photo export in v1.

## 4. Release Strategy

### 4.1 v1 (Mainline Validation)

Must ship:

- Core user flow: write text -> choose template -> preview -> export.
- Platform presets: Xiaohongshu, X, Instagram.
- Local autosave and reopen.
- High-quality launch templates (target: 8).

Should defer:

- Pro feature tiers (`19/29`) and advanced paid entitlements.
- Live Photo support.

Monetization posture:

- Keep pricing and gating minimal to avoid harming activation.
- If paid starts in v1, only keep a lightweight entry tier (e.g., `9 RMB/month`) with simple quota unlocks.

### 4.2 v1.1 (Monetization and Differentiation)

Target additions:

- Pro tiers (`19/29`) with premium templates and brand controls.
- Cloud project history (login required).
- Live Photo as an experimental feature behind a flag.

### 4.3 v1.2+ (Expansion)

Potential additions:

- More platform packs and export workflows.
- Advanced formatting controls.
- Evaluate LaTeX demand before roadmap commitment.

## 5. Core User Story (v1)

As a creator, I write my own content, choose a template, verify the preview, and export a polished image set for posting.

## 6. Functional Requirements (v1)

### 6.1 Content Input (Human-First)

- Plain text and Markdown input area.
- Basic syntax support for:
  - headings
  - paragraphs
  - lists
  - bold/italic
  - quote/code blocks (basic)
- Character and page count indicator.
- No AI-generated copy entry points in v1 UI.

### 6.2 Live Preview

- Render content into paginated cards/images.
- Switch template and update preview instantly.
- Keep editor-to-preview latency low for common article lengths.

### 6.3 Platform Presets

- One-click aspect ratio/profile switch for:
  - Xiaohongshu (default portrait preset)
  - X (post-friendly preset)
  - Instagram (feed-friendly preset)
- Preset switch updates preview and export output consistently.

### 6.4 Templates

- Launch with `8` high-quality templates.
- Template controls include at least:
  - font family
  - font size scale
  - color theme
  - spacing preset
- Templates must preserve readability and branding consistency.

### 6.5 Export

- Export single page or all pages as PNG.
- Export operation target: <= 10 seconds for normal-length posts (<= 20 pages).
- Multi-page export should support direct batch download.

### 6.6 Project Persistence

- Local autosave by default.
- Re-open and continue editing previous local project.
- Optional account linkage reserved for v1.1 cloud history.

### 6.7 Usage Limits and Pricing Baseline

- Free baseline: `5` exports/day/device, up to `20` pages/export, `3` free templates.
- v1 paid strategy can remain lightweight (`9 RMB/month`) if needed for early monetization.
- Pro-tier differentiation (`19/29`) is out of v1 scope and starts from v1.1.

## 7. Quality Requirements

- First contentful paint target: <= 2.5s on standard broadband.
- Editor-to-preview update latency target: <= 300ms for typical inputs.
- Export failure rate: < 2% in beta.
- Responsive support: desktop and mobile web.

## 8. UX Requirements

- Clean split layout:
  - left: editor
  - right: live preview
- Fast template switching (one click).
- Obvious export entry point.
- New-user onboarding: 3-step hint flow max.
- Design direction: minimal, calm, low-friction interactions.

## 9. Analytics Events (Minimum)

- `project_created`
- `markdown_edited`
- `template_selected`
- `platform_preset_selected`
- `export_clicked`
- `export_succeeded`
- `export_failed`
- `paywall_viewed`
- `upgrade_clicked`

## 10. MVP Tech Direction (Proposed)

- Frontend: React + TypeScript.
- Rendering: Markdown parser + custom pagination engine.
- Export: canvas/html-to-image pipeline.
- Backend: minimal in v1 (optional usage counter + billing hooks only).
- No AI inference services required for v1.

## 11. Acceptance Criteria (v1)

- A new user can complete `write -> template -> preview -> export` in first session without support.
- At least 1 template produces publish-ready output for long (10+ page) content.
- Exported images match preview within acceptable visual tolerance.
- Platform presets produce valid outputs without manual resizing.

## 12. Launch Readiness Checklist

- Domain + SSL configured.
- Legal pages: Terms, Privacy.
- Support channel available (email or form).
- Basic observability: error monitoring + analytics dashboard.
- Payment flow tested end-to-end (if paid is enabled at launch).

## 13. Decision Baseline Reference

Detailed sign-off package:

- `06-prd-decision-package-v1.md`
