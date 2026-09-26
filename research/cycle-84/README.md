# Cycle 84 — horizontal access in narrow Export

Andrew's narrow screenshot showed a single tall column: styles moved below output settings and the live preview disappeared. The requested behavior is a thinner dialog with all three bands still reachable by an X-axis scrollbar.

The Export body now keeps output, styles and preview side by side at their useful minimum widths (220, 260 and 360 logical pixels, plus divider handles). At widths below their combined minimum, a persistent horizontal scrollbar moves the band strip; each band retains its own vertical scrolling. The title and action footer stay fixed. The resize grip now allows the dialog down to 380 px wide within the host window. This deliberately supersedes the Cycle 83 compact single-column rule in the dialog style guide.

`./bin/build` and `./bin/test` passed (113 tests, zero failures). The Export regression drags the scrollbar thumb, checks that styles and preview remain visible at 400 px, scrolls to the preview, and checks fixed footer actions. Synthetic sample renders were captured at wide width and at narrow width with the horizontal bar at both ends. They contain no private writing.

Review images: [wide](export-wide-light.png), [narrow, output side](export-wide-light-compact.png), [narrow, preview side](export-wide-light-compact-right.png).

Known gap: the 380 px minimum is an in-window QML dialog, so it cannot exceed the app window's own bounds. The continuous preview still does not show exact PDF page breaks; use Paginated preview for that.

After the earlier Dev process exited, `./bin/prepare-dev-app` refreshed the stable QA bundle. It passed strict signature verification and launched on a disposable `/private/tmp` Markdown sample. The stopped `/Applications/Fomawrite.app` was replaced with the signed packaged app; its executable matches the package and its strict signature verification passed. The prior installed bundle was kept in a temporary backup during replacement.
