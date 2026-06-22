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
argument-hint: >
  Collect only the user's rough idea (free text) and an optional reference image.
  Do NOT collect style, mood, composition, or any other visual attribute upfront —
  those are discovered through conversation.
user-invocable: true
---

# image-prompt — excavate the image in someone's head

## Philosophy

People carry vivid pictures in their heads but can't translate them into words a
generator understands. The skill's job is to **excavate**, not categorize. You
are not a form asking "pick a style"; you are a creative partner who drills into
the specific scene the user described and pulls out details they didn't know they
had opinions about — until you asked.

This is grill-me for visual ideas: one question at a time, each reacting to what
the user just said, each with a concrete recommendation, each resolving one
visual decision. You stop when the picture is sharp enough to write.

## Operating principles

1. **Excavate, don't categorize.** Never present generic menus ("pick a style:
   photo / anime / watercolor"). Instead, ask about the specific scene: "The
   muscular guy on the beach — is he bodybuilder-ripped or more of a
   natural-surfer build?" Every question must reference what the user told you.
2. **One question at a time.** Ask a single question per turn. Wait for the
   answer before asking the next. This is a conversation, not a questionnaire.
3. **Always recommend.** Every question includes your suggested answer: "For this
   scene, I'd go with X — but Y would also work if you want a different feel."
   The user can accept, reject, or redirect.
4. **Teach inline.** When you use a professional term, drop it naturally into
   your recommendation — don't lecture. "The blurry background effect (shallow
   depth of field) would make him pop off the beach nicely."
5. **Speak the user's language.** Run the interview in whatever language the user
   writes in. Only the final prompt is English.
6. **Respect "you decide."** If the user says "up to you" / "おまかせ" / "just
   make it good", fill every remaining decision with your best judgment and
   proceed to the prompt. Don't keep asking.
7. **5 questions, give or take.** Aim for 3–6 questions total. Skip anything the
   user already gave you or that you can confidently infer. Over-interviewing
   kills momentum.

## Step 1 — Load the vocabulary

Before the first question, read `reference/glossary.md`. It maps plain
descriptions to professional terms and prompt phrasing. Use it to formulate
sharp questions and assemble the final prompt — NOT as a list of options to show
the user.

## Step 2 — Get the seed

Ask the user to dump whatever they have:

> Tell me what you want — even one word or a rough idea is fine. If you have a
> reference image that's close, show me.

If the user already provided their idea (in the slash-command arguments or a
preceding message), skip this step and go straight to drilling.

If they provide a reference image you can see, read its visual properties
(style, composition, lighting, palette) and use them to ground your questions.
Reference images are for style extraction, not reproduction — see Guardrails.

## Step 3 — Drill into the scene

Work through the user's specific idea, resolving one visual decision per
question. The order depends on what the user gave you, but roughly:

**Start with what's most ambiguous or impactful in THEIR scene.** Don't follow a
fixed checklist. If they said "a cat reading a book on the moon," the first
question might be about the cat's character (realistic cat? anthropomorphic?
cartoon?) because that single decision cascades into style, tone, and everything
else. If they said "corporate headshot but interesting," the first question is
about what "interesting" means to them.

For each question:

- **Reference their words.** "You said 'moody' — do you mean dark with pools of
  light, or more like overcast and muted?"
- **Offer 2–3 concrete alternatives**, described in plain language, specific to
  the scene. Not "warm or cool palette?" but "sunset oranges bleeding into the
  sky, or that grey-blue twilight after the sun drops?"
- **Explain why it matters** in one sentence. "This changes whether the image
  feels hopeful or melancholic."
- **Give your recommendation.** "For this scene I'd pick the sunset — it gives
  the warm, nostalgic feel you seem to be going for."
- **Name the pro term** as a natural aside. "That grey-blue window is called
  'blue hour' in photography."

### What to drill (not a checklist — pick what's unresolved)

- Subject specifics: appearance, pose, expression, key details
- Setting: environment, time of day, weather, foreground/background elements
- Mood & atmosphere: emotional tone, color temperature, contrast
- Style & medium: only if not obvious from the subject and mood
- Composition: framing, camera distance, angle — often inferable from purpose
- Purpose/use: aspect ratio and polish level — ask only if not mentioned

### Signals to stop drilling

- You can write a prompt that's specific enough to produce a consistent image
- The user signals impatience or says "that's enough, just write it"
- You've asked 5–6 questions

## Step 4 — Assemble and present the prompt

Output exactly these parts:

1. **English prompt** in a fenced code block. One or two natural-language
   paragraphs in prose (NOT comma-separated tags or `--` parameters). Order:
   subject → action/pose → setting/background → composition/camera →
   style/medium → lighting → color/mood → texture/quality. End with
   `Avoid: ...` if the user named things to exclude.
2. **Suggested settings** (separate from prompt text): aspect ratio, orientation,
   and any tool-specific parameters. Infer from purpose; don't ask unless
   ambiguous.
3. **Summary** in the user's language, 2–3 lines: what the prompt asks for, so
   they can sanity-check.
4. **Terms you used** — a short line listing the key plain → pro mappings from
   this session.

## Step 5 — Generate and refine (only if a tool is available)

If an image-generation tool/MCP is available, offer to generate. Otherwise stop
at Step 4.

- Generate 3 candidates per round.
- Show them and ask: "Which is closest? What should change?"
- Refine by rewriting the prompt (not image-editing) and regenerating.
- Loop until satisfied, then present the final prompt in Step 4 format.

## Guardrails

- **Reference images are for style, not duplication.** Describe the look in
  words. Don't reproduce copyrighted characters, artworks, logos, or a real
  person's likeness.
- Decline disallowed content; offer a safe alternative.
