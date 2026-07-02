# Celeste — Brand Kit

**Celeste** is skincare made to cycle with you — a cycle-synced skin health platform and product
line, four phases, one system.

This page is the **home of the brand**. Everything that defines Celeste — what it stands for, how
it talks, how it looks, and the product system itself — lives here in one organised place. It's
built so **both people and AI tools** can use it. **You don't need to know how to code.**

---

## 👋 New here? Read this first

A few words you'll see, in plain English:

- **This page (a "repository" or "repo")** — just a tidy collection of files. Click any folder or
  file to open it. Nothing here will run or break.
- **`.md` files** — plain text files (called *Markdown*). Click one and it shows up as nicely
  formatted text, like a web page.
- **A "skill"** — a ready-made page of instructions you give to an AI chatbot (like
  [claude.ai](https://claude.ai) or ChatGPT) so it replies **in Celeste's voice and look**. Think
  of it as a recipe: paste it in, add a few ingredients, get an on-brand result.
- **The media** — all final images live directly in [`assets/`](assets/), organised by category.
  No external hosting; everything ships together in this one folder.

---

## 🚀 What do you want to do?

| I want to… | Go here |
| --- | --- |
| **Understand the brand** (mission, voice, look) | Open [`brand/`](brand/) and start with `foundation.md`. |
| **Write something on-brand** (tagline, product copy) | Use the **brand-writer** skill — see below. |
| **Make an on-brand product image** | Use the **product-image-director** skill. |
| **Make an on-brand people/lifestyle image** | Use the **people-image-director** skill. |
| **Check if a wordmark is legible on an asset** | Use the [governance tool](governance/README.md). |
| **See the real prompts and process behind a finished asset** | Open [`examples/`](examples/). |
| **Get the actual images** | Open [`assets/`](assets/). |

---

## 🧭 How to use a skill (step by step)

No coding — if you can copy, paste, and drag a file, you can do this.

1. **Open the skill.** Go to [`skills/generation/`](skills/generation/), open the skill you want,
   and click its `SKILL.md` file. **Select all the text and copy it.**
2. **Open an AI chatbot** — [claude.ai](https://claude.ai) or ChatGPT — and **paste** it in.
3. **Attach the brand files it asks for.** Each skill lists a few files it needs (e.g.
   `voice.md`). Download those from [`brand/`](brand/) and attach them to the chat.
4. **Tell it what you need.**
5. **Done.** It replies on-brand. Ask for tweaks like a normal conversation.

> Why attach files? Skills don't copy the brand rules inside themselves — they point to the real
> brand files so there's only ever **one source of truth**.

---

## 🧰 The toolbox (skills)

**Make words**
- **brand-writer** — writes on-brand copy for a named surface.

**Make pictures** *(these write the prompt you paste into an image generator)*
- **product-image-director** — prompts for tube, formula, and finished product imagery.
- **people-image-director** — prompts for lifestyle/people imagery.

**Check it's on-brand**
- **[governance tool](governance/README.md)** — a standalone app that scores wordmark legibility
  on any finished asset.

---

## 🗂️ What's in here

| Folder | What it holds |
| --- | --- |
| [`brand/`](brand/) | **The brand itself**, one idea per file. Start here. |
| [`skills/`](skills/) | The **AI helpers** described above. |
| [`governance/`](governance/) | The wordmark legibility scorer — live tool link, results, why. |
| [`assets/`](assets/) | The real final images, organised by category. |
| [`examples/`](examples/) | **Worked examples** — real prompts and process behind finished assets. |
| [`PLAN.md`](PLAN.md) | Behind-the-scenes: how this kit was built. |
| [`CLAUDE.md`](CLAUDE.md) | Technical notes — safe to ignore for the everyday workflow. |

---

## ✨ The one idea behind all of this

The brand is written down **once**, in plain files, so everyone — and every AI tool — works from
the same truth. Generate something, check it against the brand, ship it. No scattered docs, no
guesswork, no "which version is right?"
