---
name: product-image-director
description: Creates prompts for on-brand Celeste product imagery — tubes, formula/texture references, and finished product shots. Use when the user needs an image-generation prompt for Celeste product photography.
---

# Celeste Product Image Director

Creates the prompt for on-brand Celeste product imagery. Covers two distinct modes: unbranded
texture/formula references, and fully branded finished product shots.

## Brand inputs

Read these brand files before writing a prompt (by filename — they live in `brand/`; in a web
chatbot, attach them):

- `visual/identity.md` — the tube system, label system, per-product breakdown (color, text color,
  filled dot), formula/texture per product.
- `visual/color.md` — exact hex codes. Always use hex codes, never descriptive color language alone.
- `visual/treatment.md` — shared lighting/focus/tone rules.
- `visual/photography-product.md` — composition rules for both image modes, surface rules.
- `anti-patterns.md` — the product photography avoid list.

## Inputs from the user

- **Product** (required) — Mend, Float, Opal, or Lull, or "all four."
- **Mode** (required) — texture/formula reference, or finished product shot.
- **Notes** (optional) — specific angle, arrangement, or context.

## How to write the prompt

1. Pull the exact hex code and formula description for the named product from `identity.md`.
2. Apply the shared lighting/focus/tone rules from `treatment.md` — warm directional light, sharp
   focus throughout, intimate/material/grounded tone.
3. Apply the correct composition rules from `photography-product.md` for the requested mode.
4. State the label system explicitly for finished product shots (wordmark, technical text, phase
   indicator) — never let it get pasted-on or flat.
5. Scrub against the avoid list in `anti-patterns.md` before finalizing.

## Output format

```
PRODUCT: [product name]
MODE: [texture/formula reference | finished product shot]

PROMPT: [full prompt, hex codes included]

NEGATIVE PROMPT: [what to avoid, pulled from anti-patterns.md]
```
