# Pets

Companion cats that appear in the bottom-left corner. One available per era.

---

## Overview

Pets are purchasable companions that appear in the bottom-left corner of the screen, peeking up from below. Each era has one unique cat with distinct personality and visual style. You can own all four - they line up left to right as you buy them.

---

## General Mechanics

| Property | Value |
|----------|-------|
| Location | Bottom-left corner, lined up left to right |
| Price Formula | 1000× cheapest facility in that era |
| Unlock Condition | 30 minutes spent in that era |
| Limit | Can own all 4 pets |
| Interaction | Click to hear "*meow*" |
| Bonuses | Not yet implemented |

---

## Era 1: Nikodemus

**Norwegian Forest Cat**

| Property | Value |
|----------|-------|
| Price | 15,000 (1000 × Finger Counting) |
| Unlock | Era 1 |

### Appearance
A majestic long-haired Norwegian Forest Cat with thick fur, tufted ears, and a bushy tail. Earthy brown and cream coloring matching the Mental Era palette. Occasionally stretches or grooms itself.

### Personality
Ancient and wise. Has been counting since before humans invented numbers. Watches your calculations with knowing eyes.

### Passive Bonus
*(To be determined during implementation)*

---

## Era 2: Bjartur

**British Cheshire Cat with Bowtie**

| Property | Value |
|----------|-------|
| Price | 500,000,000 (1000 × Slide Rule) |
| Unlock | Era 2 |

### Appearance
A rotund British Shorthair with the iconic Cheshire Cat grin. Wears a distinguished brass bowtie with gear motifs. Orange-tinted fur matching the Analog Era. Occasionally fades partially invisible, leaving only the grin.

### Personality
Mischievous and enigmatic. Speaks in riddles about probability and mechanical computation. May or may not actually exist.

### Passive Bonus
*(To be determined during implementation)*

---

## Era 3: Yuki

**Japanese Anime Cat**

| Property | Value |
|----------|-------|
| Price | 10,000,000,000,000 (1000 × Pocket Calculator) |
| Unlock | Era 3 |

### Appearance
Sleek white Japanese Bobtail with large expressive anime-style eyes. Blue LED collar that pulses with computation activity. Clean digital aesthetic with subtle glow effects matching Era 3's tech blue palette.

### Personality
Energetic and curious. Fascinated by screens and blinking lights. Makes excited "nya~" sounds when you solve matrix problems.

### Passive Bonus
*(To be determined during implementation)*

---

## Era 4: AINEKO

**AI Superintelligence Cat (Accelerando Reference)**

| Property | Value |
|----------|-------|
| Price | 100,000,000,000,000,000,000 (1000 × Superintelligence) |
| Unlock | Era 4 |

### Appearance
A cat-shaped constellation of light and data. Form shifts between solid and holographic. Rainbow prismatic effects matching Era 4's cosmic palette. Eyes contain swirling galaxies. Sometimes appears to exist in multiple places simultaneously.

### Personality
Unfathomably intelligent. Has already computed all possible conversations you could have. Speaks rarely but with perfect insight. May be running the universe as a subroutine.

### Lore
Reference to Aineko from Charles Stross's "Accelerando" - a robot cat that gradually uploads itself, becomes superintelligent, and eventually transcends to become a major player in posthuman civilization. In the novel, Aineko's true nature and motivations remain ambiguous throughout.

### Passive Bonus
*(To be determined during implementation)*

---

## Implementation Details

### Visual Position
- Fixed position at bottom-left of screen
- Pets peek up from below the screen edge
- Lined up left to right in order of purchase
- 80px spacing between pets
- Idle bobbing animation

### Purchase UI
- Available in upgrades section (type-pet)
- Shows countdown timer until unlock (30 min in era)
- Pink-ish left border color (#f8a)

### Animations Implemented
- Idle: Gentle up-down bobbing (petIdle keyframes)
- Hover: Scale up slightly, rise a bit
- Click: Speech bubble with "*meow*" + dual-tone beep
- AINEKO: Rainbow shimmer effect (ainekoShimmer keyframes)

### Visual Styles
- Nikodemus: Brown/tan Norwegian Forest Cat silhouette with ear tufts
- Bjartur: Grey Cheshire cat shape, rounded features
- Yuki: White with subtle blue glow, anime-style proportions
- AINEKO: Rainbow gradient with shimmer, cosmic glow effect

---

## References

- **Norwegian Forest Cat**: Ancient breed, fits primitive calculation theme
- **Cheshire Cat**: Lewis Carroll's Alice in Wonderland, fits probability/uncertainty theme
- **Anime Cat**: Japanese aesthetic, fits digital/tech culture theme
- **AINEKO**: Charles Stross's "Accelerando" (2005), fits superintelligence theme

