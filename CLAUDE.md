# TicTacToe — Project Guide

## Overview
A single-file browser-based Tic Tac Toe game with a Windows XP (2000s) visual theme. All code lives in `index.html` — no build tools, no dependencies.

## File Structure
```
TicTacToe/
├── index.html   # Everything: HTML, CSS, and JS in one file
└── CLAUDE.md    # This file
```

## Architecture
The entire app is self-contained in `index.html` with three sections:

- **HTML** — Window chrome (XP title bar, menu bar, taskbar) + game layout (two side panels + center card)
- **CSS** — Windows XP Luna theme: beveled borders, `outset`/`inset` relief, `#d4d0c8` grey palette, Tahoma font
- **JS** — Game logic, AI, and particle effects (no frameworks)

## Game Logic (JavaScript)
| Function | Purpose |
|---|---|
| `handleClick(i)` | Entry point for player moves |
| `placeMove(i, player)` | Places a piece, triggers win/draw check |
| `cpuMove()` | Triggers AI move after delay |
| `getBestMove()` | Returns best cell index based on difficulty |
| `minimax(b, depth, isMax)` | Recursive minimax for hard AI |
| `findImmediate(player)` | Finds immediate win/block for medium AI |
| `checkWin(b)` | Returns winning line array or null |
| `endGame(winner, winLine)` | Handles win/draw UI and score update |
| `resetGame()` | Clears board, resets state |
| `resetScore()` | Resets all scores and board |
| `setMode(m)` | Switches between `'cpu'` and `'local'` mode |
| `setDiff(d)` | Sets difficulty: `'easy'`, `'medium'`, `'hard'` |

## State Variables
```js
board      // Array(9) of null | 'X' | 'O'
current    // 'X' | 'O'
gameOver   // boolean
mode       // 'cpu' | 'local'
difficulty // 'easy' | 'medium' | 'hard'
scores     // { X: n, O: n, tie: n }
```

## Visual Theme
Follows the **Windows XP Luna** aesthetic. Key rules:
- Font: `Tahoma, Verdana, 'MS Sans Serif'` at 10–12px
- Buttons: `border: 2px outset #ffffff`, press → `inset`
- Background: `#ece9d8` (window), `#d4d0c8` (panels/buttons)
- X color: `#000099` (navy blue), O color: `#cc0000` (red)
- No `border-radius` > 3px — kills the era feel
- No flat buttons — the raised bevel is essential
- Desktop: Bliss-inspired gradient (blue sky + green hills)

## AI Difficulty
- **Easy** — 70% random moves
- **Medium** — wins if possible, blocks if necessary, otherwise 50% random
- **Hard** — full minimax (unbeatable)

## Particles
Canvas-based burst effect fires on every move and win. Colors match piece colors (`#3333cc` for X, `#dd2222` for O, `#aacc00` for wins). The canvas is fixed/fullscreen behind the window at `z-index: 100`.
