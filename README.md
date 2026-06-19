# egaku

Creative production skills for AI agents — turn a vague idea in your head into a
professional, ready-to-use output.

`egaku` is a Claude Code plugin (distributed as a marketplace) whose skills are
written to be **agent-agnostic**: the skill logic lives in plain, neutral
Markdown, so it works in Claude Code, Codex, and other agents alike. Only the
YAML frontmatter is Claude Code-specific, and other agents simply ignore it.

## Skills

| Skill | What it does |
| --- | --- |
| `image-prompt` | Interviews you to turn a vague mental image into a professional **English** image-generation prompt — converting your everyday words into the precise vocabulary models respond to, and teaching you those terms as you go. If an image-generation tool is available, it also generates candidates and refines them with you. |

More creative skills (e.g. landing pages) are planned under the same plugin.

## How `image-prompt` works

- Conducts the interview in **your** language; outputs the prompt in English (where
  image models are most controllable).
- Asks with concrete options instead of blank-page questions ("photo-real / anime /
  watercolor — which is closest?"), so you recognize rather than recall.
- Translates plain words into pro terms in its confirmations ("soft blurry
  background" → *shallow depth of field / bokeh*), so you learn the vocabulary
  over time.
- Accepts an optional reference image as a *style* starting point (it describes the
  look; it does not reproduce copyrighted work).
- The prompt is the deliverable. If an image-generation tool/MCP is present, it
  also generates 3 candidates per round and refines by rewriting the prompt and
  regenerating until you're happy.

## Install (Claude Code)

```
/plugin marketplace add kazukinagata/egaku
/plugin install egaku@egaku
```

Then either let it trigger automatically ("help me make an image of …") or invoke
it explicitly with the `image-prompt` skill.

## Use in Codex or other agents

The skill is a single neutral instruction file, so any agent can follow it:

- Point the agent at `skills/image-prompt/SKILL.md`, or
- Add a line to your `AGENTS.md`:
  > When the user wants to create an image or write an image-generation prompt,
  > follow the procedure in `skills/image-prompt/SKILL.md`.

Image generation is optional — if the agent has no image tool, the skill stops at
producing the prompt, which you can paste into any generator.

## Structure

```
egaku/
├── .claude-plugin/
│   ├── marketplace.json
│   └── plugin.json
├── skills/
│   └── image-prompt/
│       ├── SKILL.md            # the interview procedure (agent-neutral)
│       └── reference/
│           └── glossary.md     # plain ↔ pro-term vocabulary
└── README.md
```

## License

MIT
