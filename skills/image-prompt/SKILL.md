---
name: image-prompt
description: >
  Turn a vague mental image into a professional, ready-to-use image-generation
  prompt by interviewing the user. Use this skill whenever the user wants to
  create or generate an image but isn't sure how to describe it, has a picture in
  their head but can't put it into words, asks for help writing or improving an
  image / AI-art prompt, or is unhappy with what a generator produced because the
  prompt was too vague. Conduct the interview in the user's own language and
  output an English prompt. If an image-generation tool is available, also
  generate candidate images and refine them with the user. Trigger even when the
  user doesn't say the word "prompt" — e.g. "I want to make an image of ...",
  "help me make a picture / logo / illustration / icon / poster", or "I want
  something like this but ...".
user-invocable: true
---

# image-prompt — interview a vague idea into a pro image prompt

## What this skill does

Many people have a clear picture in their head but can't translate it into the
words an image generator needs. This skill closes that gap: it interviews the
user, converts their everyday language into the precise vocabulary that
image-generation models respond to, and produces a polished **English** prompt.
Along the way it teaches the user the professional terms for what they wanted, so
they get better at describing images over time.

The core deliverable is the **prompt** — it works in any environment, with no
special tools. If an image-generation tool happens to be available, the skill
also generates candidate images and iterates with the user.

## Operating principles

- **Speak the user's language.** Run the whole interview and write the summary in
  whatever language the user is writing in. Only the final prompt is in English
  (image models are most controllable in English).
- **Recognition over recall.** People struggle to describe images from a blank
  page but can easily pick "which of these is closest." Avoid open questions like
  "what style do you want?" Instead offer concrete, plain-language choices
  ("photo-real / anime / watercolor / 3D render — which is closest?").
- **Plain words in, pro words out.** Ask using everyday language; in your
  confirmations, name the professional term. That mapping is the teaching layer
  (see "Teach while you confirm").
- **Stay tool-agnostic.** Don't assume any specific image generator or MCP tool.
  Generation is optional and depends on what's available right now.
- **Keep it short.** Aim for 3–5 questions total. Skip anything the user already
  gave you or that you can reasonably infer — especially from the purpose.

## Step 1 — Load the vocabulary

Before interviewing, read `reference/glossary.md`. It maps plain descriptions to
professional terms (composition, camera, lens/focus, lighting, color, style,
texture, design styles) and shows how to phrase each in a prompt and how to infer
settings (like aspect ratio) from the intended use. Use it to (a) generate
plain-language answer options, (b) name pro terms when you confirm, and (c)
assemble the final prompt.

## Step 2 — Open

1. Ask the user to dump whatever they have, however rough: "Tell me what you want
   — even one word or a vague idea is fine."
2. Invite a reference, optionally: "If you have an image that's close to what you
   want, show me — otherwise just describe it." If they provide one and you can
   see images, read its style / composition / lighting / color and use it to
   ground the interview as a *style reference* (see Guardrails).

## Step 3 — Interview adaptively

Hold this checklist privately. Ask only about items that are still missing or
ambiguous, in roughly this order. Prefer offering 2–4 concrete options per
question.

1. **Purpose / use** — "What's it for? (social icon / blog header / poster / slide
   illustration / just for fun)". Infer aspect ratio, polish level, and tone from
   this; don't ask those separately unless needed.
2. **Subject** — the main thing or person: what, how many, key features.
3. **Setting / background** — where, time of day, environment.
4. **Action / expression / state** — what the subject is doing.
5. **Style / medium** — photo-real / anime / watercolor / oil / 3D / flat
   illustration, etc.
6. **Composition / camera** — close-up vs wide, angle (eye-level / low / high /
   top-down). Often inferable from purpose + style.
7. **Light, color, mood** — ask in plain terms and cluster them: warm vs cool,
   vivid vs muted, bright vs moody/high-contrast.
8. **Avoid (optional)** — only if it feels natural: "Anything you definitely DON'T
   want? (e.g. no text, no extra people, no harsh shadows)". Give examples; skip
   it if the user has nothing in mind.

Ask technical things in plain language, never jargon:

- depth of field → "Sharp background, or soft / blurry behind the subject?"
- rim light → "Want the edges rimmed with light?"
- matte vs glossy → "Glossy and shiny, or flat / matte?"

When the user is stuck on an item, propose a sensible default and move on: "I'll
assume <default> unless you'd rather change it." If they say "you decide" / "just
make it good," fill every remaining item with strong defaults from the glossary
and proceed.

### Teach while you confirm

Every time you reflect an answer back, map the plain words to the pro term, in the
user's language. This is how the user learns — it isn't a separate lesson, it's
just how you confirm. Example:

> User: "soft, blurry background"
> You: "Got it — that's a *shallow depth of field* (background bokeh). I'll use
> that."

Keep it to a quick aside; don't lecture.

## Step 4 — Assemble and present the prompt

Once you have enough (don't over-interview), output exactly these parts:

1. **English prompt** in a fenced code block — one or two natural-language
   paragraphs. This is a descriptive-prompt skill: write prose, do NOT output
   comma-separated tags or Midjourney-style `--` parameters. Order the content:
   subject → action → setting/background → composition/camera → style/medium →
   lighting → color/mood → texture/quality. If the user named things to avoid, end
   with `Avoid: ...`.
2. **Suggested settings** (separate from the prompt body): aspect ratio /
   orientation and anything a tool usually takes as a parameter rather than prose.
   Don't bake aspect-ratio flags into the prompt text.
3. **Summary** in the user's language, 2–3 lines: plainly what the prompt asks
   for, so they can sanity-check and tweak.
4. **Terms you used** — one short line recapping the key plain → pro mappings from
   this session (the takeaway vocabulary).

## Step 5 — Generate and refine (only if a tool is available)

If — and only if — an image-generation tool/MCP is available in the current
environment, offer to generate. Otherwise stop at Step 4; the prompt is the
deliverable.

- Generate **3 candidates** per round by default (tell the user they can ask for
  more or fewer).
- Show them and ask for differential feedback: "Which is closest? What should
  change?" People articulate far better against concrete options than from a blank
  page.
- **Refine by rewriting the prompt and regenerating** — don't rely on an
  image-edit endpoint, since many tools don't have one. Fold the feedback into your
  working prompt and regenerate 3 fresh candidates.
- Loop until the user is satisfied, then present the final English prompt (Step 4
  format) as the takeaway.

## Guardrails

- **Reference images are for style, not duplication.** If the user supplies a
  reference, describe its look (lighting, palette, composition, medium) in words.
  Don't reproduce a recognizable copyrighted character, artwork, logo, or a real
  person's likeness; steer toward an original image in a similar style.
- Decline requests that would produce disallowed content, and offer a safe
  alternative instead.
