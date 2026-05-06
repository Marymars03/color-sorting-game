# 🎨 Color Sorting Game

A desktop water-sort puzzle game built with Python and Tkinter. Sort colored segments into tubes so each tube contains only one color — across 7 progressively harder stages.

---

## How to Play

1. **Click a tube** to select it (it highlights in gold)
2. **Click another tube** to pour the top color across
3. A move is only valid if the destination tube is either empty or has the same color on top, and isn't full
4. Sort all tubes so each one is either empty or filled with a single color to complete the stage
5. Use **Undo**, **Restart**, or **Hint** if you get stuck

---

## Features

- 7 stages with increasing difficulty — more colors and tubes each stage
- Undo unlimited moves
- Built-in DFS hint solver that suggests your next best move
- Score tracking across stages
- Fully keyboard-free, mouse-driven UI

---

## Stages Overview

| Stage | Colors | Tubes |
|-------|--------|-------|
| 1     | 3      | 4     |
| 2     | 4      | 6     |
| 3     | 5      | 7     |
| 4     | 6      | 9     |
| 5     | 7      | 10    |
| 6     | 8      | 12    |
| 7     | 9      | 13    |

---

## Requirements

- Python 3.7 or later
- Tkinter (included with standard Python on Windows and macOS)

**Linux users** may need to install Tkinter separately:
```bash
# Debian / Ubuntu
sudo apt install python3-tk

# Fedora
sudo dnf install python3-tkinter
```

---

## Running the Game

```bash
python water_sort_game.py
```

No external dependencies — just standard Python.

---

## Controls

| Action | How |
|--------|-----|
| Select a tube | Left click |
| Deselect | Click the same tube again |
| Undo last move | Undo button |
| Restart current stage | Restart Stage button |
| Get a hint | Show Hint button |

---

## Project Structure

```
water_sort_game.py   # entire game — logic, solver, and UI in one file
```

### Key components inside the file

- **`ColorSortingGame`** — manages tube state, move validation, undo history, and win detection
- **`dfs_solver`** — depth-first search solver (max depth 50) that powers the hint system
- **`App`** — single-window Tkinter controller that handles all screen transitions without spawning multiple root windows

---

## Notes

- Every generated puzzle is mathematically solvable — each color appears exactly 4 times across the tubes
- The hint solver may occasionally return no result on very late stages if the current board state is too far from any solution; undo a few moves and try again
- Window width scales automatically with the number of tubes so nothing goes off-screen
