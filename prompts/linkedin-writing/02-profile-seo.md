# LinkedIn Profile SEO

Recruiters don't read profiles — they type a search query and look at who
comes up. If recruiters don't write to you, you're invisible to the
algorithm. Optimizing the profile is SEO for your career.

## Headline — the starting point
Formula: **Role | Domain / Tech | Value / Impact**

- One target role, not a multi-role list. `Product / Program / Project
  Manager` is searched by three different queries and matches none well.
- A niche qualifier is fine: `Senior Program Manager | HealthTech`.
- Value proposition goes last: `Senior Program Manager | Data Platforms |
  Salesforce | Delivering Enterprise Programs at Scale`.
- Use all 220 characters. Concise ≠ short; concise = every word is a keyword.
- Never put in the headline: "Looking for opportunities", "X years of
  experience", "Authorized to work in the US", "passionate / motivated".
  Recruiters don't search for those.
- A/B test: change the headline, wait a few days, compare inbound.

## Job titles in experience
- Name positions exactly as vacancies name them (`QA Engineer`,
  `Senior QA Engineer` — not `Freelance QA`).
- Strip appendages: `Marketing Manager International Markets` →
  `Marketing Manager`. Specifics belong in About, Headline, and Skills.
- Don't leave a gap as emptiness: use LinkedIn's built-in career break,
  or a stealth-startup entry.

## About
Answer three questions, with keywords and numbers:
who you are (role + specialization), what you can do (skills, tools,
industries), what you give the business (results). Add your 5 core skills
into the text.

## Skills
Up to 100 — the algorithm reads this block when ranking. Keep your two key
competencies pinned on top. Write skills the way US recruiters search them,
not literal translations.

## Experience
Outcomes, metrics, and action verbs (see `../cv-writing/02-power-verbs.md`). What you did,
what changed, which tools.

## Hygiene
- Location set and in English; professional photo.
- "Open to Work" on, follow target companies, click "Interested in" on
  company pages — you land straight in the recruiter's folder.
- The profile remembers the country it was created from, and recruiters'
  search favors local profiles — relevant if you're relocating.

## Check your visibility: Search Appearances
https://www.linkedin.com/analytics/search-appearances/ shows how often you
appeared in search, for which keywords, and from which companies. If the
keywords aren't yours — you're "not in the market". Re-check after changes.

## Audit with an LLM
Request your data export at
https://www.linkedin.com/mypreferences/d/download-my-data (takes ~a day).

**Profile audit** — feed `Profile.csv` and `Skills.csv` with this prompt:

> You are a professional data analyst and LinkedIn strategist. I want to
> optimize my LinkedIn profile to improve discoverability by recruiters and
> better reflect my professional expertise. I'm providing two files:
> Profile.csv (headline, summary, experience, education, certifications) and
> Skills.csv (skills with endorsements). Please: 1. Identify gaps or
> underused keywords relevant to my industry, role, and goals. 2. Suggest an
> improved headline using high-impact keywords. 3. Rewrite my "About" section
> to make it more compelling, human, and keyword-optimized. 4. Recommend
> additional relevant skills that are frequently searched in my field.
> 5. Suggest edits to the experience descriptions to improve keyword
> alignment. Focus on a recruiter-friendly profile that enhances search
> visibility while maintaining authenticity.

**Network audit** — feed `Connections.csv` with this prompt:

> Analyze the Connections.csv file from my LinkedIn data export to assess the
> quality, relevance, and strategic value of my professional network.
> 1. Network composition: break down my connections by industry, job title,
> seniority, and location; highlight overrepresented and underrepresented
> areas for my target direction. 2. Strategic alignment: based on my career
> goal [insert goal], determine how well my network supports it and flag
> high-impact connections (hiring managers, decision-makers). 3. Actionable
> recommendations: who to connect with (roles, industries, regions), what
> content to engage with, whether to prune, and networking tactics to
> increase visibility among relevant recruiters.
