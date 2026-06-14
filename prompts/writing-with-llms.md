# Writing With LLMs — Quality Guardrails

Career content has a specific failure mode: if your resume, About section, or
post reads like generic AI output, a recruiter pattern-matches it as "AI did
this" and trust drops. The goal is text that sounds like *you* — concrete,
first-person, specific. This file has two parts: what to make the model
*avoid*, and how to *prompt* so the output is good in the first place.

## Part 1 — Avoid AI slop

Paste this block into any content prompt as a constraint:

> When you write this, avoid all signs of generic AI text:
> - **Banned words:** delve, leverage, utilize, harness, streamline,
>   underscore, pivotal, robust, seamless, innovative, cutting-edge,
>   game-changer, landscape, realm, tapestry, synergy, testament,
>   comprehensive, vital, crucial, elevate, unlock, unleash.
> - **Banned transitions:** furthermore, moreover, consequently, notably,
>   importantly, "in today's fast-paced world".
> - **Banned constructions:** "it's not just X, it's Y", "stands as a
>   testament to", "navigating the landscape of", "in the realm of",
>   "dive into", rhetorical rule-of-three in every sentence.
> - Use plain, specific language and active verbs. Vary sentence length and
>   rhythm — don't start several sentences the same way.
> - Write in the first person with concrete details and real numbers, not
>   smooth abstractions.
> - No "Intro → three even points → Conclusion" skeleton, no emoji headers,
>   no over-polite neutral filler. Cut any sentence that adds no fact.

### Tells to self-check before you ship
- **Vocabulary:** any word from the banned list above.
- **Rhythm:** uniform paragraph length; many sentences with identical
  structure; em-dashes everywhere.
- **Shape:** the rigid intro-point-point-point-conclusion template;
  bullet lists used for everything; a labeled "Conclusion:".
- **Voice:** overly polite, neutral, hedged tone; no first-person; no
  specific anecdote, name, or number that only you could have written.
- **Emptiness:** sentences that sound impressive but state nothing
  verifiable ("a results-driven professional passionate about excellence").

If a line would fit on anyone's resume, it's slop — replace it with a fact
only true about you.

## Part 2 — How to prompt for good output

Roughly the order of impact (aligned with Anthropic's prompt-engineering
ladder):

1. **Be clear and direct.** State the exact task, the format, the length,
   and who will read it. Strip ambiguity. "Rewrite this experience bullet in
   one line, ≤20 words, for a senior backend role" beats "make this better".
2. **Give context and motivation.** Explain *why* and *for whom* — the
   target role, the company, what the recruiter is screening for. Models
   write more sharply when they know the goal.
3. **Show your voice with examples.** Paste 1–2 things you actually wrote.
   This is the single best defense against generic output — the model
   imitates real samples better than it follows "sound natural".
4. **Let it think first.** Ask for a short reasoning pass or an outline
   before the final text, then the polished version. Reasoning before
   answering improves quality on anything non-trivial.
5. **Assign a role.** "Act as a technical recruiter for [role]" or "act as my
   ghostwriter" focuses the model's judgment.
6. **Separate your data from your instructions.** Put your raw achievements
   in a clearly marked block (e.g. under a heading or in tags) so the model
   doesn't blur facts with directions.
7. **Force questions over invention.** End with: "ask clarifying questions
   where the material is thin — do not invent facts, dates, or metrics."
   Made-up numbers on a resume are a real risk.
8. **Iterate against Part 1.** After a draft, ask: "review your own draft and
   flag anything from the AI-slop list, then rewrite the weak lines."

### Materials worth knowing (searchable by name)
- Anthropic's prompt-engineering guide (in the Claude / Anthropic docs) — the
  clearest practical ladder, with examples.
- OpenAI's and Google's prompting guides — similar principles, more examples.
- Wikipedia's "Signs of AI writing" — a thorough, neutral catalog of the
  tells in Part 1, useful as an editing checklist.
