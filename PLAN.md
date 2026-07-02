# Celeste — Brand-as-Code

> **This is the source-of-truth plan for the project.** Committed to the repo so it survives
> across sessions.
>
> **Status: core build complete ✅**

## Progress checklist

- [x] Scaffold repo structure (`README.md`, `CLAUDE.md`, dirs) — modeled on a class reference
      repo (Evan's Neo Premier League brand kit)
- [x] Author the text brand source (`brand/*.md`), reconciled against the real established source
      docs (Brand Details, Brand Writer, Product + People Image Guides, Type System)
- [x] Correct factual errors surfaced during reconciliation — hex codes (Opal, Lull), wordmark
      font (Cedarville Cursive, not an earlier placeholder name), brand name casing
- [x] Build `surfaces/` — trimmed to only the two surfaces with a real, established spec
      (tube label, packaging); did not invent specs for surfaces without real source material
- [x] Build `skills/generation/` — 3 skills (brand-writer, product-image-director,
      people-image-director), each formatted from real established docs, not invented from scratch
- [x] Build `/governance` — documented the real wordmark legibility scorer (built in Gemini
      Canvas for A6): the actual prompt, the verification scale, and honest per-medium results
- [x] Populate `assets/` — 39 real final images organized into 7 categories, indexed in
      `manifest.json`, every path verified against disk
- [x] Build `examples/` — two real worked cases (tube system build, packaging build) using actual
      prompts, actual hex codes, and actual documented failures from A2-A6

## Context

**Celeste** is a cycle-synced skincare brand — the course capstone project. This repo is also
structured to mirror a class reference repo (Neo Premier League), adapted to Celeste's actual scope
and real production history rather than copying its structure wholesale.

The organizing principle: **one fact per file**, light YAML frontmatter so machines can read it +
prose so humans can, a **single canonical brand source**, and skills that reference that source by
filename rather than duplicating it.

## Decisions

- **Location:** everything — brand text, skills, governance docs, and final images — lives in this
  one repo/zip. No external media hosting; this ships as a single upload into a vibe-coding tool
  (Replit/Lovable) to generate the final site.
- **Scope over volume.** Where the reference repo this was modeled on has 10 skills and a
  `decisions/` changelog folder, this repo has 3 skills and no `decisions/` folder — because this
  is a one-shot capstone, not an ongoing, evolving brand with a maintenance history. Padding the
  structure to match the reference repo's size would have meant inventing content with no real
  source behind it.
- **Governance lives outside `skills/`.** The wordmark scorer is a standalone vibe-coded app (a
  real built tool with a live link), not a prompt-based skill — it gets its own root-level folder.
- **Assets are the real, final, curated set** — not every generation produced along the way, just
  the images that made it into the finished brand system.

## Reconciliation note

Early drafts of `brand/` were built from memory of prior sessions before the actual established
source documents (Brand Details, Brand Writer, Product Brand Image Guide, People Brand Image
Guide, Celeste Type System) were provided. Those drafts were fully reconciled against the real
docs — corrected, not merely supplemented — once the source material was available. `PLAN.md`
records this because catching and fixing that gap is itself part of the documented process.

## Site generation brief (for the vibe-coding tool prompt)

Notes to include when prompting Replit/Lovable/Claude Code to build the final site from this zip:

- **Interactive, high-end, editorial brand book** — not a static slide-deck-as-webpage. Should
  feel designed, not templated.
- **Parallax, hover states, creative interactions** — motion and interactivity are part of the
  brief, not optional polish.
- **Image-heavy, but organized** — show a lot of imagery. Where a section would otherwise have too
  many images stacked vertically, use a **carousel with pagination** instead of a long scroll.
- This zip's whole structure (`brand/`, `skills/`, `governance/`, `assets/`, `examples/`) should be
  read as the source material — the tool should pull real content and real images from it, not
  invent placeholder content.

This section is a holding note, not yet acted on — do not generate the site from this brief until
explicitly asked.
