N-Back Practice Game

## How the Program Works (User Guide)

This is a web-based implementation of the N-Back cognitive training task.

1.  **Goal:** The primary goal is to track stimuli (a letter appearing in one of nine grid positions) and determine if the current stimulus matches the stimulus presented 'N' trials ago based on position, letter, or both.
2.  **Setup:**
    *   **N-Back Level:** Choose the value of 'N' (e.g., 2-Back means comparing with the stimulus from 2 trials ago).
    *   **Interval (ms):** Set the time (in milliseconds) each stimulus is displayed before the next one appears. This also determines the time you have to respond.
    *   **Rounds to Win:** Set the total number of stimuli that need to be presented to win the game.
    *   **Start Game:** Click this button to begin the game with the selected settings. Settings are saved locally in your browser.
3.  **Gameplay:**
    *   A letter will appear in one of the 9 grid cells.
    *   A timer bar on the right indicates the remaining time to respond for the current stimulus.
    *   Compare the current letter and its position to the letter and position from N trials ago.
    *   Press the corresponding key:
        *   `N`: If **Neither** the position nor the letter matches the one from N trials ago.
        *   `L`: If only the **Letter** matches.
        *   `P`: If only the **Position** matches.
        *   `B`: If **Both** position and letter match.
    *   **CRITICAL RULE:** You MUST press one of these keys for EVERY stimulus after the first N trials. Failing to press any key will count as a mistake!
    *   **Initial Trials:** For the first N trials, no comparison is possible. The correct action is to press nothing, or press 'N'. Pressing 'L', 'P', or 'B' during these initial trials counts as a mistake.
4.  **Scoring & Mistakes:**
    *   **Correct:** Increases when you press the correct key (or correctly press nothing/N in the first N trials).
    *   **Mistakes:** Increases if you press the wrong key, or if you fail to press ANY key before the timer runs out (after the first N trials).
    *   **Score:** Increases by 10 for each correct response.
    *   **Game Over:** The game ends if you accumulate 3 mistakes.
    *   **Win:** The game ends successfully if you complete the specified "Rounds to Win" without reaching 3 mistakes.
5.  **Feedback:**
    *   The grid briefly flashes green for a correct response and red for an incorrect one.
    *   These feedback flashes last exactly 300 milliseconds.
6.  **Restarting:** After a game ends (win or lose), click "Play Again" to start a new game with the same settings. You can change settings before starting again.

## Code Structure (Developer Guide)

The application consists of three main files:

1.  **`page.html`:**
    *   **Structure:** Defines the HTML layout using semantic elements. Includes:
        *   Header (`<h1>`)
        *   Controls section (`.controls`) for setting game parameters (N-level, interval, rounds).
        *   Stats display (`.stats`) for correct count, mistakes, and score.
        *   Game area (`.game-area`) containing the 9-cell grid (`.grid-container`) and the timer (`.timer-container`).
        *   Instructions section (`.instructions`).
        *   Overlays for "Game Over" (`.game-over`) and "You Win" (`.win-screen`).
    *   **Dependencies:** Links to the external `style.css` for styling and the Canvas Confetti library for the win animation.
    *   **JavaScript:** Contains the core game logic within `<script>` tags.

2.  **`style.css`:**
    *   Contains all CSS rules for styling the elements defined in `page.html`.
    *   Uses Flexbox and Grid for layout.
    *   Defines styles for different game states (e.g., feedback indicators, overlays).
    *   Styles the timer bar animation.

3.  **JavaScript (within `page.html`):**
    *   **Initialization (`DOMContentLoaded`):** Waits for the HTML to load, then gets references to all necessary DOM elements.
    *   **State Variables:** Manages the game's state (e.g., `gameRunning`, `positionHistory`, `letterHistory`, `mistakes`, `score`, `currentTrial`, `expectedKey`, `hasResponded`, settings values).
    *   **Constants:** Defines fixed values like the available `LETTERS` and `MAX_MISTAKES`.
    *   **DOM Element References:** Stores references to frequently accessed HTML elements.
    *   **Settings Persistence:**
        *   `loadSettings()`: Reads saved settings (N-level, interval, rounds) from `localStorage` on page load.
        *   `saveSettings()`: Saves the current settings to `localStorage` whenever they are changed.
    *   **Core Game Logic:**
        *   `startGame()`: Resets the game state, updates the UI, disables controls, and calls `showNextStimulus()` to begin the sequence.
        *   `showNextStimulus()`:
            *   Checks for win condition.
            *   Clears the previous stimulus.
            *   Checks if the user missed a response in the previous trial (after N trials). Missing a response always counts as a mistake.
            *   Generates and displays the new stimulus (position and letter).
            *   Updates history arrays.
            *   Determines the `expectedKey` based on the N-back comparison.
            *   Starts the timer animation.
            *   Schedules the next call to itself using `setTimeout`.
        *   `handleKeyPress(e)`: Listens for keyboard input (`n`, `l`, `p`, `b`). Checks if the pressed key matches the `expectedKey` for the current trial (considering the initial N trials). Updates score/mistakes and provides visual feedback. Sets `hasResponded` flag.
        *   `registerMistake()`: Increments the mistake counter and checks if the game should end.
        *   `endGame()`: Stops the game loop, displays the "Game Over" screen, clears the grid, and re-enables settings controls.
        *   `winGame()`: Stops the game loop, displays the "You Win" screen (with confetti), clears the grid, and re-enables settings controls.
    *   **Helper Functions:**
        *   `showFeedback()`: Shows correct/incorrect indicators for exactly 300ms using setTimeout.
        *   `startTimer()`: Resets and starts the visual timer bar animation.
        *   `clearGrid()`: Hides any visible stimulus and feedback indicators.
        *   `enableSettings()`: Re-enables the input controls after a game ends.
        *   `updateStatsDisplay()`: Updates the score, correct count, and mistake count in the UI.
    *   **Event Listeners:** Attaches functions to events like button clicks (`start`, `restart`), key presses (`keydown`), and changes in settings inputs (`change`). 