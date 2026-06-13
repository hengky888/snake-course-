# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a simple Snake game implementation built with Python and pygame. It's a single-script project created as part of a Gemini course exercise.

**Tech Stack:**
- Python 3.x
- Pygame (cross-platform game library)

## Repository Structure

- `snake_game/main.py` - Complete game implementation (single file containing all game logic)
- `snake_game/README.md` - User-facing setup and gameplay instructions
- `snake_game/requirements.txt` - Dependency list (pygame only)
- `GEMINI.md` - Initial project documentation with architecture notes

## Building and Running

### Setup
```powershell
pip install -r snake_game/requirements.txt
```

### Running the Game
```powershell
python snake_game/main.py
```

### Testing
No automated tests currently exist. The TODO in GEMINI.md notes that unit tests for collision detection and snake growth should be implemented.

## Code Architecture

The project uses a single-script architecture with a main `gameLoop()` function that:

1. **Initialization:** Creates the snake at screen center, spawns initial food
2. **Event Handling:** Processes arrow key input for snake direction, C to restart, Q to quit
3. **Game State Updates:** 
   - Moves snake by updating position coordinates
   - Detects food collision and grows snake
   - Detects wall/self collision (triggers game over)
4. **Rendering:** Clears display, draws food, snake segments, and score
5. **Frame Timing:** Maintains 15 FPS using pygame clock

### Key Game Constants (defined at module level)
- Display dimensions: 800x500 pixels
- Snake block size: 10 pixels
- Game speed: 15 FPS
- Colors: white, yellow, black, red (loss screen), green (food), blue (background)

### Game Loop Control Flow
- Outer loop: Runs until user quits (game_over = True)
- Inner loop: Runs when game_close = True (loss screen), waits for C or Q input
- Returns True to restart, False to quit

### Data Structures
- `snake_List` - List of [x, y] coordinates for each snake segment
- Food position - Two float variables (foodx, foody) that snap to 10-pixel grid
- Score - Calculated as `Length_of_snake - 1`

## Future Enhancements

Based on GEMINI.md notes:
- Implement unit tests for game mechanics (collision detection, growth logic)
- Consider refactoring into classes if complexity increases (multiple levels, additional entities)
- Keep game constants at module top for easy difficulty/speed adjustments

## Development Notes

- Follow PEP 8 style guidelines
- Any new features should be reflected in README.md
- The game is currently production-ready for its scope; no linting tools are configured
