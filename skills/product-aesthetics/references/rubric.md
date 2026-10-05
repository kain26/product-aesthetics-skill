# Rubric v1.0

Rate each dimension 0–5 using the common anchors plus the dimension-specific tests. Keep weights fixed across product categories; adapt expectations to purpose.

| Dimension | Weight | Evaluate | Evidence for 5 | Typical evidence for 1–2 |
|---|---:|---|---|---|
| Purpose and task clarity | 15 | Can users understand the offering and locate the next action? Does form support function? | Primary task dominates appropriately; labels and action hierarchy explain what happens | Competing CTAs, unclear purpose, decorative elements obscure actions |
| Visual hierarchy and composition | 20 | Order, grouping, density, alignment, spacing, page rhythm | Clear reading order and intentional density; groups and proportions remain coherent across reviewed screens | Everything has equal emphasis; nested cards/noise, arbitrary gaps, unclear groups |
| Typography and readability | 15 | Type roles, line length, sizing, contrast of hierarchy, reading comfort | Consistent type scale; long text, labels and numbers suit their tasks | Tiny essential text, inconsistent roles, uncomfortable line length, erratic weights |
| Color and material logic | 10 | Semantic color roles, contrast, borders, shadows, gradients, surface depth | Colors communicate reliably; surface treatments serve hierarchy and brand | Random accents, illegible foregrounds, incoherent shadows or misleading depth |
| Component and cross-screen consistency | 15 | Repeated button/input/card/icon behavior and visual rules | Shared elements follow stable rules; meaningful variants are distinguishable | Same action styled several ways, mixed icon families, incompatible screen languages |
| Interaction rhythm and feedback | 10 | Discoverability, focus, loading/error/success, transition continuity | Tested journey gives timely, legible feedback; states retain context; motion serves purpose | Observed no response, jumpy transitions, inaccessible focus, state ambiguity |
| Responsive and inclusive presentation | 10 | Platform fit, reflow, zoom, target usability, keyboard and motion where tested | Intended sizes preserve priorities; essential content/actions remain usable; tested access paths work | Observed clipping/overlap, tiny targets, zoom failure, broken focus order |
| Brand coherence and distinctiveness | 5 | Fit between audience, copy, imagery, personality and function | Recognizable, appropriate visual language with consistent details | Generic elements conflict with purpose or copy; unrelated visual styles |

Common anchors:
- 0: observed fundamental breakdown throughout the reviewed scope.
- 1: severe, widespread defects; weak organizing rules.
- 2: some rules exist, but repeated problems dominate.
- 3: competent and mostly coherent, with clear unfinished areas.
- 4: strong execution; a few localized shortcomings.
- 5: exceptional coherence supported by multiple positive observations; no material issue in reviewed scope.
- U: no evidence sufficient to rate; omit from denominator.

Screenshot boundaries: interaction is U. A single desktop screenshot cannot substantiate responsive behavior; use U for that dimension unless supplied screenshots support a clearly scoped visual reflow review. Typography contrast seen by eye is an observation, not a measured WCAG result. A single page may show component consistency within that page; disclose that cross-screen consistency is untested.

Calibration examples (arithmetic, not benchmark products):
- All ratings 3 → 60/100; all 4 → 80/100. Do not describe these as identical maturity levels.
- Screenshot ratings for dimensions 1–5 and 8: 3,3,4,3,3,2. Observed weight 80; contribution 50; provisional visual score 63; coverage 80%. Interaction and responsive/inclusive presentation are U. Coverage is rubric coverage, not an assertion that 80% of product behavior was tested.
- Complete ratings 4,4,4,4,4,1,4,4 → 74/100. A blocking primary action must still be reported P0; the total cannot certify readiness.

Resolve scoring disagreements by pointing to anchors and evidence. Do not use a universal checklist of font counts, color counts, card counts, or whitespace amounts as scoring criteria.
