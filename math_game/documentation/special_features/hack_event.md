# Hack Defense Event

High-pressure security challenge that tests rapid problem-solving under time pressure.

---

## Overview

Hack events are intense 2-minute challenges that begin appearing in Era 3 once you reach Complexity 35+. Problems queue up rapidly and you must solve them before the queue overflows.

---

## Unlock Requirements

| Requirement | Value |
|-------------|-------|
| Minimum Era | 3 (Digital) |
| Minimum Complexity | 35 |

---

## Mechanics

| Property | Value |
|----------|-------|
| Duration | 2 minutes |
| Max Queue Size | 5 problems |
| Starting Interval | 4 seconds between problems |
| Minimum Interval | 1.5 seconds |
| Speed Increase | Every 15 seconds |
| Interval Reduction | 500ms per speed increase |

---

## How It Works

1. **Alert**: Ominous three-tone sound, screen overlay appears
2. **Queue**: Problems start appearing in a visible queue
3. **Solve**: You must solve problems before 5 accumulate
4. **Speed Up**: Every 15 seconds, new problems arrive faster
5. **Win**: Survive 2 minutes without queue overflow
6. **Lose**: If 5 problems queue up, event fails

---

## Outcomes

### Success
- Random bonus reward (same as bonus problem rewards)
- Prestige/achievement tracking

### Failure
- Lose 30-50% of current computations
- No other penalties

---

## Visual Design

- Dark red-tinted screen overlay with scanline effect
- Glowing red border with pulse animation
- Cyan terminal-style problem text
- Queue bar showing threat level (fills red as queue grows)
- Timer showing remaining duration

---

## Audio

| Event | Sound |
|-------|-------|
| Hack Alert | Low ominous three-tone (200Hz) |
| Hack Fail | Descending doom sequence (150Hz) |
| Queue Add | Tension tick |
| Success | Victory fanfare |

---

## Strategy Tips

- Stay calm - panicking leads to errors
- Focus on the current problem, not the queue
- Simpler problems appear at the same rate as complex ones
- Matrix problems take longer - prioritize speed over precision
- Keep your complexity high for practice before Era 3

---

## Narrative Context

In the Digital Era, your compute infrastructure becomes a target. Rogue AIs, hackers, and competing systems attempt to infiltrate and drain your resources. Successfully defending proves the robustness of your security systems.

At Complexity 40+, the narrative shifts to "Rogue AGI Exfiltration Attempt" - foreshadowing the ASI conflicts of Era 4.

