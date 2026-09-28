# Fixing line deletion in Meta's Lexical editor

[Merged PR #9247](https://github.com/facebook/lexical/pull/9247) · TypeScript · Browser selection APIs · Chromium, Firefox and WebKit

Deleting to the end of a line should work whether that line contains plain text or an embedded widget. In Chromium, an inline widget at the end of a line could cause Lexical to delete just one character instead.

For `aa|aa bbbb [X]`, where `|` is the caret and `[X]` is an inline widget, the command should leave `aa`. Instead, most of the line remained. My fix was approved and merged by Lexical maintainer `etrepum` on September 27, 2026.

## Root cause

Lexical measures a line boundary by moving a collapsed native caret. Chromium can place that caret inside the widget's own DOM text. That text belongs to a Lexical `DecoratorNode`, rather than an editable `TextNode`.

The selection resolver rejected this position, leaving the model selection collapsed. Line deletion then fell back to character deletion. The browser had found the boundary, but the editor could not represent it.

## The change

The fix normalizes that measured position to the widget's edge before applying the range. It adds 23 production lines and removes two, with no new dependency or public API.

The correction is limited to line deletion, non-isolated inline decorators, the current editor, and text inside the decorator wrapper's light DOM. Existing root and slot boundaries remain in effect.

Changing the general selection resolver could interfere with private selections inside widgets. Comparing screen rectangles would introduce layout assumptions that fail for raised or transformed content. Correcting the deletion endpoint keeps the change close to its cause and preserves collapsed native selection handling.

## Validation

The regression tests run in real Chromium, Firefox and WebKit engines. They cover both deletion directions, rich and plain text, empty widgets, direct and nested widget text, and raised alignment.

| Check | Result |
| --- | --- |
| New regression matrix on unchanged source | 8 failures, 64 passes |
| Same matrix with the fix | 72 passes |
| Separate iframe and shadow-root checks | 72 passes |
| Upstream core and extended CI | Passed |

The [core workflow](https://github.com/facebook/lexical/actions/runs/36340085929) and [extended workflow](https://github.com/facebook/lexical/actions/runs/36340551678) include Node 22/24 unit tests and browser, integration and end-to-end coverage across Linux, macOS and Windows. The PR contains the implementation, regression tests and review history.

## Scope and outcome

This defect emerged while investigating a separate soft-wrap deletion issue, [#9234](https://github.com/facebook/lexical/issues/9234). The merged change does not resolve that broader issue. It fixes a specific editing operation without relying on general assumptions about browser line geometry.

The [merge commit](https://github.com/facebook/lexical/commit/14050cff1bf1fc53ea61548f3e4621f92fdbb28f) credits my GitHub account, `maximilliangrand`. Investigated, implemented and validated with Codex assistance; independently reviewed and merged upstream.
