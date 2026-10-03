# Pac-Man for PewPlay

This directory contains the original static game adapted for the PewPlay game template. Open `index.html` to play.

`game.json` holds the game page text. `preview.png` and `cover.png` provide the page images. The PewPlay workflow checks pushes to `preview` and `main`.

Game controls: Guide Pac-Man through the maze, collect dots and avoid ghosts. Eat a power pellet to turn the tables for a short time.

## Second pass (2026-10)

Changes are made directly in `pacman.js` (the `src/` folder is the owner's untouched development copy and is no longer in sync with it).

- Layout: the canvas fills the window at any size/orientation, scaled to fit and centred on black, rendered at the device pixel ratio (crisp on retina). Outside practice mode the unused side/top margins are cropped so the maze is bigger.
- Touch: Pointer Events everywhere; on-screen D-pad, pause and sound buttons placed below the maze (portrait) or beside it (landscape); swipe anywhere still works. Canvas buttons use correct coordinates after scaling.
- Sound: on/off button (and `M` key), saved in `Pac-Man:muted`; sounds and the game pause when the page is hidden or loses focus (with a "Paused" overlay). Sounds are loaded once into memory.
- Saves: high scores stored in `Pac-Man:highScores` (old unprefixed saves are not imported).
- Fixes: `M` (skip level) now only works in practice mode; `Enter` on a menu with nothing highlighted selects the first option.
