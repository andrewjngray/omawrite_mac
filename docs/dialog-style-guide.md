# Fomawrite dialog layout guide

Use this guide for larger task dialogs such as Export. Small confirmations and native file pickers can keep their platform layout.

## Structure

1. Give the dialog one short title, one sentence of context only when it helps, and a stable footer. The footer holds the primary action at the right, Cancel immediately to its left, and any separate secondary workflow at the far left.
2. Keep primary and Cancel actions the same height and width. Use a clear filled primary color; secondary actions have a quiet but visible fill and border at rest, a stronger hover state, and a visible keyboard focus state. Labels describe the result, such as “Save PDF…” or “Paginated preview…”.
3. Put an action beside the content it affects. Preview modes and paginated preview belong in the preview band, style duplication in the style band, and output settings in the options band. Avoid isolated buttons after long explanatory paragraphs.
4. Let long bands scroll independently. Reserve at least 16 px of separation between a scrollbar and the nearest interactive control. Scrollbars stay inside their own band and never overlap headings or cards.
5. Large dialogs can resize within their parent window and expose a visible lower-right resize grip. Bands use draggable splitters with minimum widths. If those widths exceed the dialog, keep the bands side by side and show a horizontal scrollbar beneath them. Header, footer, and primary action remain visible while content scrolls.

## Export dimensions and behavior

- Open near 1100 × 720 logical pixels, bounded by the available app window. Allow the outer frame to resize down to 380 px wide and up to the host window margin.
- In three-band mode, start with roughly 28% options, 29% styles, and the remaining space for preview. Options must stay at least 220 px, styles 260 px, and preview 360 px wide. Splitters have a generous grab area but a quiet one-pixel rule.
- Below the combined band minimums, keep all three bands visible in one horizontal strip. Show a persistent X-axis scrollbar to reach styles and preview. Never shrink band controls below their useful widths or hide a band to fit the frame.
- Footer actions are 36 px high; Cancel and Save share a 136 px width. The footer stays fixed when the dialog or a band is scrolled.
- Preview is a continuous approximation. State that concisely near its Paginated preview action; do not imply that the live area is page-exact.

Check the dialog at wide and minimum window sizes, with long style names, in light and dark themes, by mouse and keyboard. Confirm that resize and splitter drags cannot hide controls or move the dialog outside the window. Do not use a visual-only label to imply a working action.
