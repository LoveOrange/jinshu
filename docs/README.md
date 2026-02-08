# Jinshu Documentation

## Structure

- `01-product`: product definition, scope, and decision baseline.
- `02-architecture`: technical architecture and design decisions.
- `03-development`: engineering execution and testing strategy.
- `04-release`: launch and post-launch operation documents.

## Read Order (Onboarding)

1. `01-product/01-vision.md`
2. `01-product/02-product-process.md`
3. `01-product/03-story-map.md`
4. `01-product/04-scope-matrix.md`
5. `01-product/05-prd-v0.md`
6. `01-product/06-prd-decision-package-v1.md`
7. `01-product/07-decision-log.md`
8. `02-architecture/01-platform-tradeoffs.md`
9. `03-development/01-acceptance-tests-v1.md`
10. `04-release/01-launch-roadmap-4-weeks.md`

## Evolution Order (Delivery Phases)

1. Product definition: `01-product/*`
2. Architecture decisions: `02-architecture/*`
3. Development execution: `03-development/*`
4. Publish and iteration: `04-release/*`

## Naming Rules

- Prefix each document with a numeric order: `NN-topic.md`.
- Keep one responsibility per document.
- Prefer updating existing docs over creating overlapping versions.

## AI Context Bundle (Recommended)

When asking AI to implement work, include these files first:

- `01-product/01-vision.md`
- `01-product/04-scope-matrix.md`
- `01-product/05-prd-v0.md`
- `01-product/07-decision-log.md`
- `02-architecture/01-platform-tradeoffs.md`
- `03-development/01-acceptance-tests-v1.md`
- Relevant phase file (for example `02-architecture/*` or `03-development/*`)
