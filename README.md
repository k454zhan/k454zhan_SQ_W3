# Week 3 Example 2: Full Fighting Game

## What This Example Demonstrates

> **Note for students:** This section is included in example files only to help you study. Do not include it in your Side Quest submissions.

This example builds on Example 1 by adding health, attacking, hit detection, sound, and game states to create a complete two-player fighting game.

- **Game states** — the game is always in one of three states (`STATE_START`, `STATE_FIGHT`, `STATE_WIN`); each state controls what gets drawn and what responds to input; stored as constants to prevent typos
- **`preload()`** — loads all sounds before the sketch starts so they are ready to play immediately; there is one punch effect used for every hit
- **Punch sound** — `punchSound` loads the single energy punch asset and plays it each time a fighter attacks
- **Health system** — each fighter has a `health` property that decreases when hit; `maxHealth` is stored separately so health bars can be drawn proportionally using `map()`
- **`startAttack()`** — called from `keyPressed()` so the punch fires once per press; sets the direction of the fist based on the opponent's position
- **`getPunchX()`** — a method that returns the fist's x position; used in `checkHits()` to test whether the punch connects with the opponent
- **`takeHit()`** — called on the fighter being hit; blocked punches deal no damage; health reaching zero triggers `endGame()`
- **Hit flash** — `hitFlash` counts down from 12 each time a fighter is hit; while it is above zero, the blob draws white instead of its normal colour
- **`hitLanded` flag** — prevents the same attack swing from registering more than one hit per punch
- **`keyPressed()` vs `keyIsDown()`** — `keyPressed()` fires once per press and is used for attacks and menu navigation; `keyIsDown()` fires every frame and is used for movement and blocking
- **Health bars with `map()`** — `map()` converts health (0 to maxHealth) to a bar width in pixels (0 to barW); the bar shrinks as health decreases
- **Start and win screens** — drawn using text and shapes in their respective game states; a semi-transparent overlay is used on the win screen

## Setup and Interaction Instructions

To run the sketch locally, open `index.html` in Google Chrome using Live Server.

Sound files must be present in `assets/sounds/` before running:

- `energypunch.mp3`
- `victory.mp3`
- `new_background.mp3`

**Player 1 Controls:**

- Move: A / D
- Attack: F
- Block: G

**Player 2 Controls:**

- Move: Arrow Keys
- Attack: K
- Block: L

Press **ENTER** to start or rematch.

**Opening the Chrome Console**

- **Windows:** Press `F12` or `Ctrl + Shift + J`, then click the **Console** tab
- **Mac:** Press `Cmd + Option + J`

The console will show any errors in your sketch.

## Assets

| File                               | Source                                            |
| ---------------------------------- | ------------------------------------------------- |
| `assets/sounds/energypunch.mp3`    | Energy punch sound effect — OpenGameArt.org       |
| `assets/sounds/victory.mp3`        | Victory tune — Pixabay                            |
| `assets/sounds/new_background.mp3` | Matthew Pablo, Space Dimensions — OpenGameArt.org |

## References

[1] Hemz. n.d. A Yellow Round Light and Light [Photograph]. Pexels. Retrieved August 7, 2026 from https://www.pexels.com/photo/a-yellow-round-light-and-light-10187003/

[2] Alex_Jauk. 2024. Victory Tune [Sound Effect]. Pixabay. Retrieved August 7, 2026 from https://pixabay.com/sound-effects/musical-victory-tune-185252/

[3] Yodguard. 2026. Short Energy Beam Shot (4) [Sound Effect]. Pixabay. Retrieved August 7, 2026 from https://pixabay.com/sound-effects/film-special-effects-short-energy-beam-shot-4-482500/
