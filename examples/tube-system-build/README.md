---
title: Worked Example — Tube System Build
type: example
status: active
updated: 2026-07-01
source: A2, A3, A4, A5, A6, governance
---

# Worked example — Tube System Build

A real, end-to-end account of how the Celeste tube system went from a moodboard to a governed
final asset. Not a hypothetical skill chain — this is the actual path, spanning five assignments.

```
moodboard → control prompt (A2) ─▶ scaffold test A/B (A3) ─▶ spot treating breakthrough (A4)
    ─▶ formula-locking sequence (A5) ─▶ tube branding execution (A6) ─▶ governance check ─▶ ✅ shipped
```

## Step 1 — Moodboard → control prompt (A2)

Rather than jumping straight to prompting, the process started with a moodboard of reference
images. Claude was asked to identify the characteristics being gravitated toward — crop, lighting
quality, skin texture, how product interacted with skin — which informed the control prompt written
by hand:

> "A close-up, tight-crop image of a woman with textured, freckled skin applying a swipe of
> skincare to her cheek using her fingers. There is warm, golden light in the frame, and we can
> only see half of her face. The skincare is glowy, textured, and the photo is warm, intimate, and
> demonstrative of the skincare on her face."

This ran across four models (GPT Image 2, Midjourney, Nano Banana, Seedream 4.5) as a control test,
then again with per-model refined prompts in round two, after Claude revisited the moodboard and
tailored each version to what had been observed about each model's behavior.

## Step 2 — Scaffold test A/B (A3)

Two directions were tested head-to-head on the 4-tube lineup: a lighter/warmer background and
shadow treatment (Test A) against a darker/moodier one (Test B).

**Test A, version 2 prompt (excerpt):**

> "Restyle this image (ZBASEIMG) using the lighting and background signals from ZSTYLEREF only.
> Keep all tube colors, product textures, drip behaviors, composition, and crop exactly as they
> appear in ZBASEIMG. From ZSTYLEREF apply only: the background color (#DCD3CB), and the shadow
> behavior shown in the top crop of ZSTYLEREF — each tube casts a soft diffused shadow directly
> behind it on the background wall, slightly darker at the base of each tube and fading upward,
> warm toned not grey or cold."

**Finding:** color transferred reliably once a hex code was added (the same lesson that shows up
repeatedly across the whole project — see `visual/color.md`). Shadow/lighting behavior was much
harder to control through prompting alone, and stayed subtle regardless of how explicitly it was
described. Generating a custom shadow reference and feeding it back in caused the model to copy the
pattern exactly rather than treat it as a lighting environment to interpret.

**Outcome:** Test A (lighter, warmer) was locked as the Celeste aesthetic going forward — the
direction now codified in `visual/treatment.md`.

## Step 3 — Spot treating breakthrough (A4)

The bigger unlock came from spot treating: selecting specific zones of an output (formula color,
product placement) and regenerating only those zones, rather than the whole image. This made it
possible to lock in each product's tube color and formula texture independently before scaling
across all four products.

## Step 4 — Formula-locking sequence (A5)

With spot treating established, the formula system was built in a deliberate sequence:

1. **Lock the formula swatches** — four products, four distinct textures, each realistic and
   distinct enough to read as different formulas, believable enough to read as skincare.
2. **Combine swatch + tube** — once a texture was locked, the corresponding tube was introduced.
   Started with one product, got the pairing right, then used that as the template.
3. **Make product behavior believable** — composition alone wasn't enough; the formula coming out
   of the tube had to match the swatch in amount, motion, and weight.
4. **Scale one to four** — with one product fully dialed in, it became the direct reference for
   building the next. Each product informed the next; the system compounded rather than starting
   over each time.

See `assets/swatches/` for the four locked formula swatches and `assets/squeeze-drip/` for the
product-in-motion shots that resulted from this sequence.

## Step 5 — Tube branding execution (A6, Medium 01)

With the formula system locked, branding execution followed its own deliberate sequence:

**Establishing what needed to live on each tube:** phase indicator (dots near the cap), wordmark,
technical details (product name + associated phase).

**Wordmark typeface exploration:** three options were tested directly on a locked tube mockup —
Cedarville Cursive, Nunito Sans, and Comfortaa — using previously created artifacts as in-situation
mockups. Cedarville Cursive was chosen (see `visual/typography.md`).

**Executing in Fuser:** finalizing cap look and feel, scaling the tube and applying branding, then
mocking up all four together.

**What worked (four real lessons):**

1. **Treat products like characters.** Finalize individual tubes before compositing into larger
   scenes — the same logic as finalizing a character before placing them in a scene.
2. **Name and label with intention.** Non-dictionary "code" names (e.g. `MNDCUT`, `OPLBOXFINAL`,
   `oplcut`, `OPLBOXBLANK2`) kept the machine from accidentally rendering them as real text, and
   made everything easier to reference and execute precisely.
3. **Hex codes, all the way.** Descriptive language alone never held — "warm white," "olive green,"
   "grey blue" were too loose. Locking specific hex codes and referencing them consistently was key.
   Example from the actual prompt: *"matte opaque white #FFF7E6, with the cursive celeste wordmark
   in slate blue #8392AF"* — precise enough to hold across regenerations.
4. **"Do not render" labels.** Annotation labels in the working file kept the model from
   accidentally rendering the callout text itself into the final image.

The finished tubes from this sequence live in `assets/tubes/` — see `visual/identity.md` for the
full per-product breakdown (hex codes, text colors, label system).

## Step 6 — Governance check (A6)

The finished tube lineup was run through the wordmark legibility scorer (see `/governance`):

**Result: 3 — "Perfect wordmark match."** The tool found the wordmark clearly legible across all 4
tubes, even at small scale and across 4 different background colors. Color and curvature didn't
compromise legibility.

## What this demonstrates

- **One source of truth.** Every step traces back to the same locked brand system — nothing was
  reinvented per touchpoint.
- **Explore, then lock, then scale.** The moodboard and A/B test came first; only after a direction
  was chosen did the formula-locking sequence begin.
- **Generate → govern.** The tube system wasn't considered finished until it passed a real
  legibility check, not just a visual eyeball test.
- **Real limitations, documented honestly.** Color transfer via hex code was reliable; shadow and
  lighting behavior were not, and that limitation is recorded rather than hidden.
