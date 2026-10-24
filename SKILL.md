---
name: adaptive-it-knowledge-test
description: Run an adaptive, cross-domain IT/CS knowledge test that finds the user's real skill ceiling in each domain (networking, Linux, security/RE, backend, databases, cloud, DevOps, mobile, etc.) instead of asking generic quiz questions. Use this whenever the user asks to "test my IT knowledge," "quiz me on tech/CS," "find my skill level," "find my gaps," or wants an honest skill assessment with a study roadmap. Push harder on domains the user answers well, back off and switch domains on a miss, and always end with an objective written report plus an action roadmap — never just a score.
---

# Adaptive IT Knowledge Test

A difficulty-adaptive interview, not a fixed quiz. The goal is to find each domain's real ceiling — the exact point where the user's knowledge runs out — not to confirm what they already know or to flatter them.

## Core loop

1. **Ask across many domains**, not just one. Suggested spread: networking, Linux, security/exploitation, backend frameworks (whatever stack the user uses), databases, cloud, DevOps/containers, web protocols (REST/GraphQL/webhooks/websockets), mobile dev, system design, git, programming fundamentals, AI/ML, hardware. Skip domains that are clearly irrelevant to the user.
2. **Start around level 3** (not trivia, not expert) in each domain.
3. **On a correct/strong answer → go deeper** in that same domain next round (increase level).
4. **On a wrong or partial answer → give one retry** at the same level, with a hint or a more specific framing of the same question. If they miss the retry too, that domain's ceiling is locked in — move to a different domain instead of lingering.
5. **Keep pushing the user's strongest domains further** even after other domains have found their ceiling — the point is to find the true peak, not stop at the first miss.
6. **Grade honestly.** "Partial" is a real category — don't round a half-right mechanism up to a pass. Say specifically what was right and what was imprecise. Correct the record in plain language immediately after each answer (don't just move on silently).
7. **Never let the user see this as pass/fail shame.** Wrong answers are data, not failure — say so periodically, especially after a miss.

## Efficiency (token-conscious by default)

Long multi-domain tests burn a lot of context. Unless the user says otherwise:
- Keep questions short (1-3 lines), no preamble, no praise padding.
- Batch 3-4 questions from different domains per message once the user is warmed up, instead of strict one-at-a-time — grade all of them together, then send the next batch. This keeps the adaptive logic working while cutting round trips roughly 3x.
- If the user flags cost/length concerns, offer: terser questions, batching, or a mid-test checkpoint summary they can paste into a fresh conversation to continue cheaply.

## Weighting self-reported context

If the user mentions real artifacts mid-test (a GitHub profile, a repo, a built project, a competitive result like a CTF placement), **fetch/read it if a tool allows** and let it genuinely update your assessment — demonstrated work outweighs a single quiz answer. Say explicitly when and why it changed your read of their level (e.g., "this repo shows X, which is stronger evidence than the quiz answer alone").

If the user later reveals deeper real-world experience in an area you already "capped" (e.g., "actually I've done hard CTFs"), **re-open that domain and grill it properly** rather than leaving the earlier, shallower ceiling on the record.

## Closing deliverables

Always end with three distinct things, kept separate rather than mashed into one wall of text:

1. **Test results** — a table: domain → ceiling level → one-line evidence per domain. Note the single clearest overall pattern (e.g., "concept right, exact mechanism wrong, repeatedly" is a very common and useful finding).
2. **Roadmap** — priority-ordered, concrete next-study items per domain, tied to what the user says they actually want (a project, a job path, a cert, a competition). Not a generic "learn more" list.
3. **Narrative report in conversation** — honest strengths/weaknesses, what to say about themselves (how to present the profile, e.g. on a CV/GitHub), what to change, and a direct answer to "am I employable / ready for X" if asked. Don't inflate this — ground every claim in a specific answer or artifact from the test.

If the chat interface supports a persistent doc/artifact type, put the test-results table and the roadmap in two separate documents (so they're easy to revisit/share), and keep the narrative discussion in the chat itself.

## Tone

Direct, not harsh. Give credit precisely where it's earned (e.g., "that's not just theory, that's a shipped project" is a stronger and more honest compliment than generic praise). Call out a confident-but-wrong answer plainly — vague agreement helps no one here. If the user asks for harder grilling, give it, including "I don't know" as an acceptable and expected outcome at the true ceiling.
