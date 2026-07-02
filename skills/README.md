# skills/ — LLM tools that use the brand

Each skill is a folder with a `SKILL.md`. A skill never hard-codes brand text; it names the
`brand/` files it needs by filename in a `## Brand inputs` section. To run one in a web LLM
chatbot, paste the `SKILL.md` and attach the named brand files.

```
skills/
└── generation/
    ├── brand-writer/            copy for a named surface
    ├── product-image-director/  prompts for product/tube/formula imagery
    └── people-image-director/   prompts for lifestyle/people imagery
```

Governance lives separately — see `/governance` at the repo root for the wordmark legibility
scorer (a standalone vibe-coded app, not a prompt-based skill).
