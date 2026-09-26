# Cycle 82 — export scrollbar and action states

Andrew's Cycle 81 screenshots showed a small scrollbar mark overlapping the “Built-in styles” heading and secondary export actions that looked like plain text. The export gallery and options scrollbar are now explicitly placed at the right edge of their respective scroll views, with no default track decoration. Style cards and secondary actions have a visible resting fill and border; hover adds the established accent border. The Split and Full controls in the export preview now switch between a read-only Markdown/source split and full rendered preview, rather than doing nothing.

`./bin/build` passed. `./bin/test` passed 113 tests with no failures or skips, including the export dialog layout check and a new check that Split reveals the source pane and Full hides it. `./bin/package-mac` produced a locally signed ordinary bundle and strict signature verification passed. The existing Applications app was not replaced. Direct visual review at Andrew's display scale remains open because the running Dev bundle must be closed normally before it can be refreshed. No private document screenshot was captured.

The runnable packaged build is `dist/Fomawrite.app`; the stable Dev identity is pending refresh. [Review exercise](../usability/cycle-82.md).
