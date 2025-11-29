# Problem Types

## Notation Guide

| Notation | Meaning | Example |
|----------|---------|---------|
| `1d` | 1-digit number (1-9) | 7 |
| `2d` | 2-digit number (10-99) | 42 |
| `3d` | 3-digit number (100-999) | 256 |
| `4d` | 4-digit number (1000-9999) | 1337 |
| `0.X` | Decimal with 1 digit (0.1-0.9) | 0.7 |
| `0.XX` | Decimal with 2 digits (0.10-0.99) | 0.42 |
| `vec` | Vector operation | [a,b] + [c,d] |
| `mat` | Matrix operation | A × B |

---

## Important Rules

### Two-Decimal Precision
All answers involving non-integer results must be given to exactly 2 decimal places:
- Decimal arithmetic (0.X ÷ 0.X = 2.00)
- Probability calculations
- Matrix inverse entries
- Square roots
- Matrix equations with non-integer solutions

### No Double Multiplication
Problems of the form `a op b op c` never have two multiplication operations.
Valid patterns:
- `a × b + c`
- `a × b - c`
- `a + b × c`
- `a - b × c`
- `a + b + c`
- `a + b - c`

Invalid (never generated):
- `a × b × c`

---

## Complexity Level Progression

Complexity level determines which problem types can appear.
At complexity N, problem types 0 through N-1 are available.

**Selection**: 20% chance for the hardest type (N-1), 80% uniform across easier types.

**Threshold Formula**: `threshold(n) = 100 × 1.05^(n-2)` for n ≥ 2

---

## Problem Types by Complexity

| # | Category | Format | Example |
|---|----------|--------|---------|
| 1 | Arithmetic | 1d + 1d | 3 + 5 = 8 |
| 2 | Arithmetic | 1d - 1d | 7 - 3 = 4 |
| 3 | Arithmetic | 1d × 1d | 4 × 6 = 24 |
| 4 | Arithmetic | 2d + 2d | 23 + 45 = 68 |
| 5 | Arithmetic | 1d ± 1d ± 1d | 5 + 3 - 2 = 6 |
| 6 | Arithmetic | 1d × 2d | 7 × 12 = 84 |
| 7 | Arithmetic | 2d ÷ 1d | 36 ÷ 4 = 9 |
| 8 | Arithmetic | 1d op 1d op 1d | 3 × 4 + 2 = 14 |
| 9 | Arithmetic | 3d + 3d | 234 + 567 = 801 |
| 10 | Arithmetic | 1d × 3d | 8 × 125 = 1000 |
| 11 | Arithmetic | 3d - 3d | 543 - 321 = 222 |
| 12 | Arithmetic | 3d ÷ 1d | 729 ÷ 9 = 81 |
| 13 | Arithmetic | Mixed ops | 4 ÷ 2 + 3 = 5 |
| 14 | Arithmetic | 2d × 2d | 23 × 17 = 391 |
| 15 | Arithmetic | 2d op 2d op 2d | 12 × 8 + 15 = 111 |
| 16 | Arithmetic | 4d + 4d | 1234 + 5678 = 6912 |
| 17 | Decimal | 0.X + 0.X | 0.3 + 0.5 = 0.8 |
| 18 | Decimal | 0.X - 0.X | 0.7 - 0.3 = 0.4 |
| 19 | Decimal | 0.X × 0.X | 0.4 × 0.5 = 0.20 |
| 20 | Decimal | 0.X ÷ 0.X | 0.6 ÷ 0.3 = 2.00 |
| 21 | Decimal | 0.XX + 0.XX | 0.25 + 0.37 = 0.62 |
| 22 | Decimal | 0.XX - 0.XX | 0.85 - 0.42 = 0.43 |
| 23 | Decimal | 0.XX × 0.XX | 0.25 × 0.40 = 0.10 |
| 24 | Probability | P(A∩B) independent | P(A)×P(B) = |
| 25 | Probability | P(A∪B) exclusive | P(A)+P(B) = |
| 26 | Probability | P(¬A) | 1 - P(A) = |
| 27 | Probability | P(A∪B) general | P(A)+P(B)-P(A∩B) = |
| 28 | Probability | P(A\|B) | P(A∩B)/P(B) = |
| 29 | Probability | Mixed decimal | 0.X op 0.X op 0.X |
| 30 | Probability | Bayes' Theorem | P(A\|B) from priors |
| 31 | Linear Algebra | 2D vec add | [a,b] + [c,d] |
| 32 | Linear Algebra | 2D vec sub | [a,b] - [c,d] |
| 33 | Linear Algebra | 2D scalar mult | k × [a,b] |
| 34 | Linear Algebra | 3D vec add | [a,b,c] + [d,e,f] |
| 35 | Linear Algebra | 2D linear combo | k₁[a,b] + k₂[c,d] |
| 36 | Linear Algebra | 3D scalar mult | k × [a,b,c] |
| 37 | Linear Algebra | 2D dot product | [a,b] · [c,d] |
| 38 | Linear Algebra | 3D vec sub | [a,b,c] - [d,e,f] |
| 39 | Linear Algebra | 2×2 mat × vec | M × v |
| 40 | Linear Algebra | 3D dot product | [a,b,c] · [d,e,f] |
| 41 | Linear Algebra | 3D triple add | v₁ + v₂ + v₃ |
| 42 | Linear Algebra | 2×2 mat add | A + B |
| 43 | Linear Algebra | 3×3 mat × vec | M × v |
| 44 | Linear Algebra | 2×2 mat mult | A × B |
| 45 | Linear Algebra | 3×3 mat add | A + B |
| 46 | Linear Algebra | 3×2 × 2×3 | A₃ₓ₂ × B₂ₓ₃ |
| 47 | Linear Algebra | 3×3 mat mult | A × B |
| 48 | Linear Algebra | Mat mult + add | A × B + C |
| 49 | Linear Algebra | Mat-Mat-Vec | A × B × v |
| 50 | Mixed | Linear equation | ax + b = c, solve x |
| 51 | Mixed | 2×2 Inverse | A⁻¹ (2 decimals) |
| 52 | Mixed | Quadratic roots | x² + bx + c = 0 |
| 53 | Mixed | Powers of 2 | 2^n for n ∈ [1,30] |
| 54 | Mixed | Matrix equation | Solve Ax = b |
| 55 | Mixed | Squares | n² for n ∈ [10,99] |
| 56 | Mixed | Cubes | n³ for n ∈ [2,20] |
| 57 | Mixed | Square root | √n (2 decimals) |
| 58 | Mixed | Large division | 4d ÷ 2d (integer) |
| 59 | Mixed | Sum of squares | a² + b² |
| 60 | Mixed | Factorial | n! for n ∈ [1,8] |

---

## Input Types

| Type | Format | Inputs |
|------|--------|--------|
| Simple | Single number | 1 |
| Decimal | Number with decimals | 1 |
| Vector2 | [x, y] | 2 cells |
| Vector3 | [x, y, z] | 3 cells |
| Matrix2×2 | [[a,b],[c,d]] | 4 cells |
| Matrix3×3 | 3×3 grid | 9 cells |

**Navigation**: Tab moves between matrix cells. All cells must be filled for auto-check.
