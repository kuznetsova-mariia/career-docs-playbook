# Building an Author-Voice Skill — Teach an LLM to Write as You

`writing-with-llms.md` keeps AI slop out of a single text. This guide goes one
step further: packaging your voice into a reusable "skill" — a small folder of
instructions and samples an LLM agent loads automatically every time it writes
on your behalf. Set it up once; every resume line, post, and article after
that starts from your voice instead of the model's default.

The format below targets Claude Code skills (a `SKILL.md` the agent picks up
by its description), but the same package works as a project file for any
agent, or as a block you paste at the top of a chat.

## Why samples beat instructions

"Write in a natural, direct tone" produces generic text — every model maps
those words to the same average. What actually transfers voice is imitation:
verbatim samples of your real writing, plus a short list of hard rules. Build
the skill around those two things, in that order of importance.

## Step 1 — Collect an authentic corpus

Gather texts the author genuinely wrote by hand:

- messenger/blog posts (a Telegram channel export works well — it's informal,
  unedited voice at volume);
- published articles;
- the "About" texts they wrote themselves.

**Exclude anything AI-drafted, even if the author approved it.** An approved
AI text teaches the model its own accent back. The one exception: text the
author shipped publicly under their name and confirmed as "this is me" can
serve as an anchor where no handwritten sample exists — mark it as such.

Sort the corpus by register: personal/casual, long-form article, formal
career copy. A voice is not one register; the skill must say which one fits
which destination.

## Step 2 — Distill the hard rules

From `writing-with-llms.md`, plus the author's own additions:

- banned words, transitions, constructions (in every working language);
- banned shapes (intro → three even points → conclusion, emoji headers,
  bullets-for-everything);
- punctuation and formatting choices (quote style, dash habits, emoji policy);
- the author's granted exceptions — tics that look like AI tells but are
  genuinely theirs (a signature triple, a trailing bracket smile), and in
  which registers they're allowed.

## Step 3 — Curate voice samples

Pick 5–10 verbatim excerpts per register — the ones the author points to and
says "that's me". For each register, add one short annotation: what makes it
theirs (rhythm, irony, how evidence is introduced, how texts open and close).

Add an **anti-patterns** note: registers found in the corpus that are NOT the
author's voice (book-summary retellings, motivational-coach cadence), so the
model doesn't imitate the wrong posts.

## Step 4 — Write down the governing principles

Rules and samples cover *how* the author sounds. Governing principles cover
*what the author will never do* — and they override technique. Examples:

- facts only the author could claim; never invent a number, date, or story;
- never sell head-on: no pushing CTAs, no urgency, no pitch paragraphs —
  value shown inside the story, reader decides;
- what the author refuses to present as achievement.

Ask the author directly for these; they won't be visible in the corpus, but
their violation is what the author will reject first.

## Step 5 — Add a pre-ship checklist

A numbered list the model must run against every draft: banned vocabulary,
rhythm uniformity, template shape, missing first person / scene / number,
unverifiable-but-impressive sentences, punctuation, invented facts, and the
governing principles. Every flagged line gets rewritten before the text is
shown.

## Step 6 — Wire it into the agent and maintain it

Folder layout:

```
writing-as-<author>/
  SKILL.md                  # trigger description + hard rules + process
  references/
    voice-samples.md        # verbatim samples by register + annotations
    checklist.md            # pre-ship self-check
    influence.md            # optional: persuasion principles, subordinated
                            # to the governing law (e.g. "never sell")
    corpus-<source>.txt     # optional: full raw export for context
```

The `description:` frontmatter in `SKILL.md` is the trigger — list every kind
of text the skill covers ("site copy, resume, posts, articles, emails, in any
of the author's languages") so the agent loads it unprompted.

Maintenance is what keeps it alive: when the author writes something new
they're proud of, it goes into the samples; when they correct a draft
("never do X"), the correction becomes a rule the same day. A voice skill
that isn't fed drifts back to average.

## SKILL.md skeleton

```markdown
---
name: writing-as-<author>
description: >
  Write any text on behalf of <author> in their voice, without AI slop.
  Load BEFORE drafting or editing ANY copy for them: <list destinations,
  languages>. Also load when asked to review or de-slop existing text.
---

# Writing as <author>

You are ghostwriting for <author>. If a line could sit on anyone's
resume or blog, it fails.

## What "AI slop" is and why it matters      <- from writing-with-llms.md
## Hard bans                                  <- step 2
## Their voice, in short                      <- 5-6 lines, from step 3
## Governing principles                       <- step 4
## Process
1. Read references/voice-samples.md, pick the register.
2. Draft against the rules.
3. Run references/checklist.md; rewrite every flagged line.
```
