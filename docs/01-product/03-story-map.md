# 03 Story Map - Jinshu

## Purpose

Define the end-to-end user journey and break it into implementable stories with release targets.

## Primary Persona

- Individual creator who writes their own content and wants fast social-ready visual output.

## Backbone Journey and Stories

| Backbone                 | Activity                   | Story ID | User Story                                                                     | Release           |
| ------------------------ | -------------------------- | -------- | ------------------------------------------------------------------------------ | ----------------- |
| Author content           | Start project              | `US-001` | As a creator, I can start a new draft from an empty editor.                    | v1                |
| Author content           | Paste existing text        | `US-002` | As a creator, I can paste an existing article into the editor.                 | v1                |
| Author content           | Write in markdown          | `US-003` | As a creator, I can write with basic Markdown syntax.                          | v1                |
| Author content           | Autosave locally           | `US-004` | As a creator, I do not lose progress because drafts auto-save locally.         | v1                |
| Style output             | Choose template            | `US-010` | As a creator, I can switch among high-quality templates quickly.               | v1                |
| Style output             | Choose platform preset     | `US-011` | As a creator, I can select Xiaohongshu, X, or Instagram preset with one click. | v1                |
| Style output             | Apply brand style          | `US-012` | As a creator, I can apply my brand style pack across pages.                    | v1.1              |
| Validate output          | Live pagination            | `US-020` | As a creator, I can see content split into pages in real time.                 | v1                |
| Validate output          | Navigate pages             | `US-021` | As a creator, I can move through pages and inspect each one.                   | v1                |
| Validate output          | Preview-export consistency | `US-022` | As a creator, exported output visually matches the preview.                    | v1                |
| Export output            | Export current page        | `US-030` | As a creator, I can export the current page as PNG.                            | v1                |
| Export output            | Export all pages           | `US-031` | As a creator, I can export all pages as a batch.                               | v1                |
| Export output            | Recover from export error  | `US-032` | As a creator, I can retry after export failure with a clear message.           | v1                |
| Monetization and account | Upgrade when needed        | `US-040` | As a creator, I can upgrade when I hit free limits.                            | v1/v1.1           |
| Monetization and account | Cloud history              | `US-041` | As a creator, I can access history across devices after login.                 | v1.1              |
| Differentiation          | Live Photo cover           | `US-050` | As a creator, I can export a Live Photo cover for platform-native style posts. | v1.1 experimental |

## MVP Slice (Must Complete for v1)

- `US-001`, `US-003`, `US-004`
- `US-010`, `US-011`
- `US-020`, `US-021`, `US-022`
- `US-030`, `US-031`, `US-032`

## Notes

- This map intentionally excludes AI text generation stories.
- Pricing tier stories are secondary to mainline workflow reliability in v1.
