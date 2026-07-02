---
title: Worked Example — Packaging Build
type: example
status: active
updated: 2026-07-01
source: A6, Medium 02
---

# Worked example — Packaging Build

A real account of how the Celeste box (outer packaging) was built, once the tube system was
already locked. This is a distinct process from the tubes — different failure mode, different fix.

```
natural language attempt (failed) ─▶ find + strip a reference ─▶ lock one product
    ─▶ reuse as reference for the other three ─▶ scale across angles/layouts ─▶ ✅ shipped
```

## Step 1 — Natural language alone fell short

The first attempt was plain description: *"photorealistic tall rectangular skincare box, slight
3/4 angle view."* This didn't produce the shape and angle needed. Both GPT and Gemini were tried,
stress-testing which model handled the request better — neither natural-language attempt held up.

## Step 2 — Find a reference, strip the noise

A real visual reference (an unrelated skincare box, "Botane") worked, but only after removing
extraneous signal — competing branding, in this case — leaving just shape and angle. That stripped
reference became `OPLBOXREF`, composited with the target product.

## Step 3 — Lock one, then reuse it as reference

For each new shot (the pair composite, the front-on box), one product was solidified first, then
that exact result was used as the "how" reference to generate the same shot for the other three.
Every finished asset became the next building block — the same compounding logic used in the tube
formula-locking sequence (see `examples/tube-system-build/`), applied here to packaging geometry
instead of formula texture.

The working render was then scaled across all four products, across multiple angles and layouts
(box alone, 3/4 angle, horizontal, box+tube pair) — see `assets/packaging/`.

## What this demonstrates

- **Different medium, same underlying principle.** Lock one instance, then use it as the reference
  for scaling — this pattern recurs across the whole project (formulas in A5, packaging here),
  because it works.
- **Know when natural language isn't enough.** Plain description failed outright; a stripped visual
  reference succeeded. Recognizing which situations need a reference image versus a text prompt is
  part of directing the tool, not a workaround.
- **Real limitation, documented.** The first real attempt failed and is shown here rather than
  omitted — the fix (stripping a reference to shape/angle only) is the actual lesson.
