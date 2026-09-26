# Cycle 83 — export dialog layout redesign

Andrew's Cycle 82 screenshot showed that a succession of small button and scrollbar changes had left Export visually inconsistent. The new [dialog style guide](../../docs/dialog-style-guide.md) defines hierarchy, action sizing, scrollbar gutters, resizable bands, a fixed footer and compact behavior for larger task dialogs.

The Export dialog now opens as a bounded, resizable pane with a visible lower-right grip. Its options, styles and preview bands use draggable splitters and enforce useful minimum widths. Below the three-band threshold, output settings and styles form one scrolling column. Each scrollbar stays in its own reserved gutter, away from controls. Cancel and Save have the same width and height. Split/Full sit in the preview header, and Paginated preview sits beside a concise continuous-preview label. The content and underlying Markdown/export logic are unchanged.

`./bin/build` passed; `./bin/test` passed **113 tests, zero failures and zero skips**. The export UI regression tests actual mouse drags of the resize grip and first band splitter, equal footer action sizes, minimum band widths, compact switching, and Split/Full behavior. `./bin/package-mac` and `./bin/prepare-dev-app` completed; both local bundles passed strict signature verification. The refreshed Dev app launched on a disposable Markdown sample. Synthetic dialog renders were inspected in [wide light](screenshots/export-wide-light.png), [compact light](screenshots/export-compact-light.png) and [wide dark](screenshots/export-wide-dark.png). They contain no private writing.

Native visual acceptance at Andrew's display scale remains open. The outer dialog is bounded by the parent window rather than being an independent macOS window. Export's live preview remains continuous and does not display exact PDF page breaks; the paginated preview action is available for that check.

Runnable artifacts: `dist/Fomawrite Dev.app` for review and `dist/Fomawrite.app` as the packaged ordinary build. The installed `/Applications/Fomawrite.app` remains at Cycle 82 until review.

[Review exercise](../usability/cycle-83.md).
