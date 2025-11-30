# Bonus Problems

Random timed challenge events that appear during gameplay with special rewards.

---

## Overview

Bonus problems are special timed challenges that randomly appear every ~5 minutes. They offer high-value rewards for quick solving.

---

## Mechanics

| Property | Value |
|----------|-------|
| Average Interval | 5 minutes |
| Minimum Interval | 2 minutes |
| Duration | 20 seconds |
| Difficulty | Based on current complexity (capped at 15) |

---

## Rewards

Three possible rewards, randomly selected:

### 2× Computations
Instantly doubles your current computation stockpile.

### 5× Facility Speed
All facilities produce at 5× rate for 2 minutes.
Visual indicator shows remaining duration.

### 10× Solve Value
All problems solved give 10× compute for 1 minute.
Visual indicator shows remaining duration.

---

## Visual Design

- Popup appears in center of screen
- Pulsing green border with glow effect
- Large countdown timer
- Reward preview shown before solving
- Input field for answer

---

## Audio

- 700Hz double-beep when bonus appears
- Standard correct sound on solve
- No penalty for wrong answers (timer just continues)

---

## Strategy Tips

- Keep an eye out for the popup
- Bonus problems are slightly easier (capped complexity)
- 2× Computations is best when you have high stockpile
- Facility boost is best when you have many facilities
- Solve boost is best when actively grinding

