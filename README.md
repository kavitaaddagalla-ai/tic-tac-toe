# Tic Tac Toe

A single-file browser-based Tic Tac Toe game with a CPU opponent that plays using the **minimax algorithm**.

## Features

- **Human vs CPU** — You play as X, the computer plays as O
- **Unbeatable AI** — CPU uses minimax, so the best outcome for you is a draw
- **Score tracking** — Wins, losses, and draws persist across rounds
- **Win highlight** — Winning cells pulse to indicate the winning line
- **Dark theme** — Clean, responsive UI with no dependencies

## How to Run

No build step, server, or dependencies required. Just open the file in any browser:

```bash
# Windows
start tictactoe.html

# macOS
open tictactoe.html

# Linux
xdg-open tictactoe.html
```

## How to Play

1. Click any cell to place your mark (X)
2. The CPU automatically responds with O
3. First to get three in a row — horizontally, vertically, or diagonally — wins
4. Click **New Game** to reset the board (scores are kept)

## Project Structure

The entire project is a single self-contained file: `tictactoe.html`

| Section | Description |
|---|---|
| `<style>` | Dark-themed UI using CSS Grid for the 3×3 board |
| `<body>` | Static markup — 9 cell divs, score display, status line |
| `<script>` | Vanilla JS game logic + minimax AI, no frameworks |

### Key JavaScript Concepts

- `board` — flat 9-element array (`''`, `'X'`, or `'O'`)
- `wins` — hardcoded array of the 8 winning index triplets
- `checkWinner()` — scans win conditions; returns winner, draw, or null
- `minimax()` — recursive algorithm that evaluates all possible moves to pick the optimal one
- `cpuMove()` — uses minimax scores to select the best available cell
- `init()` — resets board and DOM; scores persist via the `scores` object

## Repository

GitHub: [kavitaaddagalla-ai/tic-tac-toe](https://github.com/kavitaaddagalla-ai/tic-tac-toe)
Branch: `master`
