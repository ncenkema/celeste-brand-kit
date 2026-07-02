---
name: people-image-director
description: Creates prompts for on-brand Celeste lifestyle/people imagery. Use when the user needs an image-generation prompt showing a person using Celeste product.
---

# Celeste People Image Director

Creates the prompt for on-brand Celeste people/lifestyle imagery — the product-on-skin moment.

## Brand inputs

Read these brand files before writing a prompt (by filename — they live in `brand/`; in a web
chatbot, attach them):

- `visual/treatment.md` — shared lighting/focus/tone rules.
- `visual/photography-people.md` — who, crop/framing, expression, product-on-skin, skin rendering.
- `anti-patterns.md` — the people photography avoid list.

## Inputs from the user

- **Product** (optional) — which Celeste product is being applied, if relevant.
- **Notes** (optional) — specific crop, expression, or context.

## How to write the prompt

1. Specify a real, diverse woman 25-40 with natural, unretouched skin — visible pores, freckles,
   texture. Bare faced, no makeup.
2. Apply the crop rule: never a full face portrait. Tight crop only — half face, eyes only,
   jawline, neck, forearm, shoulder, collarbone. ECU or BCU framing.
3. Specify expression: quiet relief, calm, understated ease — not performed happiness, not blank.
4. Make the product-on-skin moment central and never incidental: the swipe, the drop, the
   application, with a realistic amount of product and natural hand positioning.
5. Apply the shared lighting/focus/tone rules from `treatment.md`.
6. Scrub against the avoid list in `anti-patterns.md` before finalizing.

## Output format

```
CONTEXT: [what's being shown]

PROMPT: [full prompt]

NEGATIVE PROMPT: [what to avoid, pulled from anti-patterns.md]
```
