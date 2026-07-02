# governance — the Celeste wordmark legibility scorer

**Live tool:** https://gemini.google.com/share/2a65c8236884?skid=1d1c9c34-61ea-4f5f-bf1b-ba458b435d07

## What it does

A custom-built web tool that checks if a target element — the Celeste wordmark — is actually
legible and identifiable in a finished asset. Upload the target, upload the test image, get a
score.

## Why it was built

Wordmark legibility was a recurring struggle across every medium — curved tubes, distant
billboards, compositing onto a booth wall. This tool gives a consistent, reusable way to check it
instead of eyeballing it each time and getting subjective results.

## How it was built

Built in Gemini Canvas using a simple deterministic-leaning prompt (mirroring Evan's example from
Lesson 9): upload a Target image and a Test image, then return a score of 0-3 with a one-sentence
explanation.

**Original prompt:**

> Create a mini web app with a clean, simple, side-by-side image comparison layout, similar in
> style to a minimal product showcase site — rounded corners, soft neutral background, generous
> whitespace, simple sans-serif labels. Two upload boxes side by side, labeled "Target" and "Test
> Image." The uploaded images themselves should be the visual focus — large, clear, with everything
> else (buttons, labels, background) staying minimal and out of the way. Below the side-by-side
> comparison, after both images are uploaded, analyze whether the element shown in the target image
> is present and legible in the test image. Return one of the following scores prominently
> displayed, along with one sentence of reasoning: 0 = not found, 1 = found, not legible (fail),
> 2 = found, slightly warped or rough (pass with caution), 3 = found, clear and strong (pass). Keep
> the UI minimal otherwise — no extra navigation, no distracting colors, just the comparison and the
> result.

Iterated once to ignore color differences between target and test (score based on shape/lettering/
legibility match only, not color), and again to add a recommended adjustment whenever a score comes
in under 3.

## Verification scale

| Score | Label | Meaning |
| --- | --- | --- |
| 0 | Not Found | The element does not appear in the test image |
| 1 | Found, Not Legible | Fail |
| 2 | Found, Slightly Warped or Rough | Pass with caution |
| 3 | Found, Clear and Strong | Pass |

## Results across all four A6 touchpoints

| Touchpoint | Score | Reasoning |
| --- | --- | --- |
| Medium 01 — Tubes (4-tube lineup) | 3 | "Perfect wordmark match" — clearly legible across all 4 tubes, even at small scale and across 4 different background colors. Color and curvature didn't compromise legibility. |
| Medium 02 — Packaging (Float box) | 0 → 2 (after iterating) | First run scored 0 — the tool flagged a shape mismatch caused by the wordmark's vertical rotation on the box, not an actual legibility problem. Re-prompted the tool to account for rotation; second run scored 2, pass with caution. |
| Medium 03 — Billboard | 2 | "Legible wordmark detected" — busiest test yet (trees, shadows, a pedestrian, wordmark appearing twice at different scales). Tool still recognized the wordmark's structural integrity despite the clutter. |
| Medium 04 — Product Display Booth | 2 (tested twice) | Tested with the large "Celeste" sign included, and again cropped to exclude it — both scored 2. Confirms the small, repeated wordmark instances on the booth are legible on their own; the pass isn't just riding on the big sign. |

## Why the mixed scores were kept

These results are shown honestly, including the failures and the caution-level passes. A mixed
scorecard that reflects real limitations demonstrates stronger critical analysis of the AI
generation process than an all-pass result would — the point of governance is catching where the
system breaks, not proving it never does. The Medium 02 case in particular is a good example: the
first-run 0 wasn't a real failure, it was the tool itself missing rotation-handling, which is exactly
the kind of thing a governance pass should surface.

## Build notes

Built and published for Assignment 6 (Multi-Touchpoint Stress Test) as the required governance
rule/skill/app for the final capstone (Constraint 3).
