# diffview

A client-side, two-textarea text diff viewer. Paste "before" and "after"
text, click Compare, and see a line-by-line diff with additions and
removals highlighted.

Live: https://sidcore-dev.github.io/diffview/

## Why

Sometimes you just want to compare two blobs of text — a config file, a
paragraph, a code snippet — without installing anything or pasting into
a third-party service. diffview does the comparison locally in your
browser.

## How it works

The diff is computed with a longest-common-subsequence (LCS) line diff,
implemented from scratch in vanilla JavaScript: a dynamic-programming
table of LCS lengths between the two line arrays is built, then walked
to classify each line as unchanged, added, or removed. There is an
"ignore leading/trailing whitespace" option that compares trimmed lines
while still displaying the original text.

## Static, client-side tool

This is a single self-contained `index.html` file — no build step, no
server, no external scripts or libraries. Everything (markup, styles,
the diff algorithm) lives in that one file and runs entirely in your
browser; the text you paste is never sent anywhere. You can open
`index.html` directly from disk, or use the hosted version above.

## License

All rights reserved. This code is public for viewing and reference only —
no license is granted to use, copy, modify, or redistribute it. See
[LICENSE](LICENSE) for details.
