# 01 Acceptance Tests v1

## Purpose

Define executable acceptance criteria for v1 mainline workflow.

## Scope

- Release target: v1.
- In scope flow: `write -> template -> preview -> export`.
- Out of scope: AI writing, Live Photo, Pro `19/29` entitlements.

## Conventions

- `AT-*`: acceptance test ID.
- Priority: `P0` for release blockers, `P1` for important but non-blocking.
- Format: Given / When / Then.

## Acceptance Tests

### `AT-001` New draft and typing (`P0`)

Given a first-time user opens the editor  
When the user enters plain text or Markdown  
Then the draft appears in the editor without errors and local autosave starts automatically.

### `AT-002` Basic Markdown render (`P0`)

Given a draft includes heading, paragraph, list, bold, italic, and quote  
When preview renders the draft  
Then all supported syntax is rendered correctly and no unsupported syntax crashes render.

### `AT-003` Real-time pagination (`P0`)

Given a draft long enough for multiple pages  
When the user continues typing  
Then preview repaginates within the performance target and page order remains stable.

### `AT-004` Template switch (`P0`)

Given a multi-page draft with one selected template  
When the user switches to another template  
Then all pages update consistently and content remains readable.

### `AT-005` Platform preset switch (`P0`)

Given a draft in preview mode  
When the user switches preset between Xiaohongshu, X, and Instagram  
Then aspect ratio updates correctly and pagination/export dimensions follow the selected preset.

### `AT-006` Export single page (`P0`)

Given a rendered draft page  
When the user exports current page as PNG  
Then a PNG is downloaded successfully and visual output matches preview.

### `AT-007` Export all pages (`P0`)

Given a rendered multi-page draft  
When the user exports all pages  
Then all pages are exported in order and operation finishes within target for <= 20 pages.

### `AT-008` Export error handling (`P0`)

Given export encounters a recoverable failure  
When failure occurs  
Then the user sees a clear error and can retry without losing draft content.

### `AT-009` Local reopen (`P0`)

Given a user has an autosaved local draft  
When the user reloads or reopens the app  
Then the most recent local draft can be restored.

### `AT-010` No AI writing entry points (`P0`)

Given v1 build UI  
When user scans input and command surfaces  
Then there is no AI write/rewrite button, prompt box, or AI output insertion path.

### `AT-011` Free limit behavior (`P1`)

Given a free user reaches daily export limit  
When the user triggers another export  
Then export is blocked with clear limit message and upgrade entry is shown.

### `AT-012` Analytics baseline events (`P1`)

Given user completes create/edit/template/preset/export actions  
When each action occurs  
Then corresponding analytics event is emitted exactly once per action trigger.

## Traceability

| Test ID  | Story IDs                    | Capability IDs                  |
| -------- | ---------------------------- | ------------------------------- |
| `AT-001` | `US-001`, `US-003`, `US-004` | `CAP-001`, `CAP-002`, `CAP-008` |
| `AT-002` | `US-003`                     | `CAP-002`                       |
| `AT-003` | `US-020`                     | `CAP-004`                       |
| `AT-004` | `US-010`                     | `CAP-006`                       |
| `AT-005` | `US-011`                     | `CAP-005`                       |
| `AT-006` | `US-030`                     | `CAP-007`                       |
| `AT-007` | `US-031`                     | `CAP-007`                       |
| `AT-008` | `US-032`                     | `CAP-007`                       |
| `AT-009` | `US-004`                     | `CAP-008`                       |
| `AT-010` | `US-003`                     | `CAP-003`                       |
| `AT-011` | `US-040`                     | `CAP-010`, `CAP-011`            |
| `AT-012` | `US-001`, `US-030`           | `CAP-015`                       |

## Release Gate

v1 release requires all `P0` acceptance tests passing.
