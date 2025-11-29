# TOTAL GAME PROGRESS (DO NOT EDIT CLAUDE)
    - Problems (Good)
    - Facilities (
    - Aesthetic (Not great. Will fix later)



# Computation Factory - Master Documentation

A math-based incremental game where solving mental math problems builds a computing empire spanning from primitive tally sticks to multiversal scale superintelligences.

---

## Game Overview

| Era | Name | Aesthetic | Facilities |
|-----|------|-----------|------------|
| 1 | Mental | Human calculation (stone, bone, paper) | 6 facilities |
| 2 | Analog | Mechanical devices (gears, engines) | 6 facilities |
| 3 | Digital | Electronics → AI (silicon, quantum) | 6 facilities |
| 4 | ASI | Cosmic computing (Dyson, Matrioshka) | 6 facilities |

---

## Core Mechanics

### Two Independent Progression Systems

#### Eras (1-4)
- Unlocked by buying at least one of every facility in the current era
- Controls: aesthetics, news bar content, available upgrades, new facilities
- Each era has 6 facilities that must all be purchased to unlock the next era

#### Complexity Levels (1-60)
- Based on total problems solved
- Formula: `threshold(n) = 100 × 1.05^(n-2)` for n ≥ 2
- Level 1: 0 problems
- Level 2: 100 problems
- Level 3: 205 problems (100 + 105)
- Level 4: 315 problems (100 + 105 + 110)
- ...and so on with 5% growth

Complexity controls:
- Which problem types can appear (1-60)
- Visual symbol flicker effects
- Bit display (2^complexity)

### Computations
Primary currency. Earned by:
- Solving problems (base: 1 per solve, modified by upgrades)
- Passive generation from facilities

### Problem Selection
When generating a problem at complexity level N:
- 20% chance: Problem type N (the hardest unlocked)
- 80% chance: Uniform random from types 1 to N-1

### Facilities
Buildings that generate computations per second. Each purchase increases next cost by 15%.
Only the next unbought facility in each era is visible.

### Upgrades
Permanent multipliers to solve value or facility efficiency.
Unlocked based on current era.

### Bonus Problems
Random events appearing every ~5 minutes with special rewards:
- **2× Computations**: Double current stockpile
- **5× Facility Speed**: 2 minutes of boosted production
- **10× Solve Value**: 1 minute of boosted solving

### News Bar (Era 2+)
Displays era-appropriate headlines that rotate every 45 seconds.
Different news banks for each era phase (early/mid/late).

### Hack Defense Event (Era 3, Complexity 35+)
Security events that require rapid problem solving:
- **Duration**: 2 minutes
- **Mechanic**: Problems queue up; if 5 accumulate, you lose
- **Speed**: Increases every 15 seconds
- **Success**: Random bonus reward
- **Failure**: Lose 30-50% of computations

---

## Complexity Visual Flicker

The symbol flicker in the left panel evolves every 4 complexity levels:

| Complexity | Display Style | Speed |
|------------|---------------|-------|
| 1-4 | Slowly changing digits (0-9) | 800ms |
| 5-8 | Faster digits | 500ms |
| 9-12 | Symbols (#?%&@!) | 300ms |
| 13-16 | Mixed symbols + digits | 200ms |
| 17-20 | Mathematical symbols (∑∏∫√) | 200ms |
| 21-24 | Mixed math symbols | 120ms |
| 25-28 | Math + Greek | 120ms |
| 29-32 | 2×2 symbol matrix | 80ms |
| 33-36 | 3×3 matrix, faster | 80ms |
| 37-40 | 3×3 matrix, Greek | 50ms |
| 41-44 | Angelic glyphs begin | 50ms |
| 45-48 | Full angelic glyphs, multicolor | 30ms |
| 49-52 | Rapid angelic + Greek | 30ms |
| 53-56 | Maximum intensity | 30ms |
| 57-60 | Transcendent flickering | 30ms |

---

## Number Abbreviations

| Symbol | Value | Name |
|--------|-------|------|
| K | 10³ | Thousand |
| M | 10⁶ | Million |
| B | 10⁹ | Billion |
| T | 10¹² | Trillion |
| Q | 10¹⁵ | Quadrillion |
| Qi | 10¹⁸ | Quintillion |
| Sx | 10²¹ | Sextillion |

---

## Audio

| Event | Sound |
|-------|-------|
| Correct Answer | 520Hz beep (60ms) |
| Bonus Problem | 700Hz double-beep |
| Era Unlock | Rising three-tone fanfare |
| Purchase | 380Hz confirmation beep |
| Hack Alert | Low ominous three-tone |
| Hack Fail | Descending doom sequence |

---

## Save System

- Auto-saves every 5 seconds
- Offline progress: 50% efficiency, max 8 hours
- Save key: `computation_factory_v9`

---

## Debug Features

- **Click era number**: Advance to next era
- **Click bit display**: Add 100 to solved count (increase complexity)
- **Click computations**: Double current amount
- **Settings → Reset**: Full game reset with confirmation

---

## File Structure

```
math_game/
├── page.html          # Main game
├── style.css          # Styling
├── config.json        # All numerical values
├── assets/
│   └── backgrounds/   # Era background images
└── documentation/
    ├── master.md              # This file
    ├── story_and_aesthetics.md
    ├── problems.md
    └── upgrades_and_facilities.md
```
