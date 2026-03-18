# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the Game

Open the file directly in any browser:
```bash
start tictactoe.html       # Windows
open tictactoe.html        # macOS
xdg-open tictactoe.html   # Linux
```

No build step, server, or dependencies required.

## Architecture

The entire project is a single self-contained file: `tictactoe.html`. It has three sections inline:

- **CSS** (`<style>`): Dark-themed UI using CSS Grid for the 3×3 board. Classes `.x`, `.o`, `.taken`, and `.win` are toggled by JS to reflect state.
- **HTML** (`<body>`): Static markup — 9 `.cell` divs with `data-i` indices 0–8, score display spans, and a status line.
- **JavaScript** (`<script>`): Vanilla JS, no frameworks. Key pieces:
  - `board` — flat 9-element array (`''`, `'X'`, or `'O'`)
  - `wins` — hardcoded array of the 8 winning index triplets
  - `checkWinner()` — scans `wins`; returns `{ winner, line }` or `{ winner: 'Draw' }` or `null`
  - `init()` — resets `board`, `current`, `over`, and DOM classes
  - Click handler on each cell drives all game logic; score counters persist across `init()` calls via the `scores` object

## Git & GitHub

- Remote: `https://github.com/kavitaaddagalla-ai/tic-tac-toe`
- Branch: `master`

**After every meaningful change, commit and push immediately.** This ensures no work is ever lost and every state is revertible.

```bash
git add <file>
git commit -m "feat|fix|chore|docs: short description of what changed and why"
git push
```

Commit conventions:
- `feat:` — new feature or visible behavior change
- `fix:` — bug fix
- `chore:` — tooling, config, or non-functional change
- `docs:` — documentation only

Never batch unrelated changes into one commit. Each commit should represent one coherent unit of work so individual changes can be reverted cleanly.
