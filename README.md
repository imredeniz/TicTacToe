# Tic Tac Toe

A single-file browser Tic Tac Toe game with a polished dark UI, animated side panels, and particle effects.

## How to Play

Open `index.html` in any modern browser — no server or install required.

## Features

### Game Modes
- **vs Computer** — play as X against an AI opponent
- **2 Players** — local pass-and-play on the same device

### AI Difficulty
| Level | Behaviour |
|-------|-----------|
| Easy | Plays randomly 70% of the time |
| Medium | Will win or block immediately, otherwise random |
| Hard | Perfect play via minimax — unbeatable |

### Effects
- **Move** — ripple ring, cell pop animation, and a particle burst in the player's colour
- **Win** — winning cells light up one by one, each firing a green particle burst; the winner's score counter bounces; their side panel flashes
- **Draw** — the board shakes and gold particles scatter from every cell

### UI
- Three-column layout: X player panel | board | O player panel
- Side panels show the player's symbol (with glow), win count, orbiting rings, and an active-turn pulse indicator
- Animated ambient background with drifting colour orbs and a star field
- Score tracking persists across games until manually reset

## Controls

| Button | Action |
|--------|--------|
| **New Game** | Clears the board and starts a fresh round |
| **Reset Score** | Zeroes all scores and starts a fresh round |

## Browser Compatibility

Works in any modern browser (Chrome, Firefox, Edge, Safari). No dependencies.
