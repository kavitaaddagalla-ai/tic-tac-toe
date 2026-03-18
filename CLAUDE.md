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
- Commit with descriptive messages (`feat:`, `fix:`, `chore:`) and push to save a revertible snapshot.
