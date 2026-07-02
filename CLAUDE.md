# CLAUDE.md

This file provides guidance to Claude (or any AI tool) when working with this repository.

## What this repo is

The canonical, machine-readable source of truth for the **Celeste** brand (cycle-synced skincare),
plus a small set of LLM "skills" that use it. See [`README.md`](README.md) for the human overview
and [`PLAN.md`](PLAN.md) for the build story.

## The one rule that matters most

**There is a single canonical brand source: [`brand/`](brand/). Never duplicate brand text.**

- All brand facts live once, in `brand/`. One fact per file.
- Skills must **not** copy brand text into themselves and must **not** reference brand files by a
  relative path. Instead a skill names the files it needs **by filename only** (e.g. "read
  `voice.md` and `lexicon.md`"). This keeps skills portable: in Claude Code the agent locates the
  named files in `brand/`; in a web chatbot the user attaches them.

## File conventions

- Every file in `brand/` starts with light **YAML frontmatter** (`title`, `type`, `status`,
  `updated`, `source`) followed by prose. Tools read the frontmatter; humans read the prose.
- Filenames are lowercase-kebab in `brand/`, all-caps in `assets/` (matching the established
  non-dictionary asset-naming convention — see `brand/lexicon.md`).
- `surfaces/` only contains files for surfaces with a real, established spec (tube label,
  packaging). Do not add invented surface specs.

## Media lives inside the repo

Unlike a repo that points to external media hosting, all final Celeste images are committed
directly in [`assets/`](assets/), indexed by [`assets/manifest.json`](assets/manifest.json). This
repo ships as a single zip into a vibe-coding tool, so keeping media local (rather than externally
hosted) is the simpler, faster choice for this project's scope. Refer to assets by **id** from the
manifest, or by filename directly.

## Working norms

- **One source of truth over invention.** If a spec, skill, or surface isn't actually established
  for Celeste, don't build a placeholder for it — leave it out. (E.g. `surfaces/` only has 2 files,
  not the 8 a larger, longer-running brand might accumulate.)
- **Governance lives separately from skills.** The Celeste governance tool
  (`/governance`) is a standalone vibe-coded app, not a prompt-based skill — it isn't in
  `skills/governance/`.
- **Visuals are user-supplied, not inferred.** Color hex values, fonts, and which hero assets to
  include come from the user's actual produced work. Do not infer them from descriptions alone;
  when in doubt, ask, then record the answer.

## Skill anatomy

Skills live at `skills/generation/<name>/SKILL.md`. Each has: frontmatter (`name`, `description`),
a `## Brand inputs` section (files needed, by filename), an input contract, and an output format.
Use `skills/generation/brand-writer` as the reference pattern.
