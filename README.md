# Adaptive IT Knowledge Test (Claude Skill)

An adaptive IT/CS knowledge test for Claude that finds your **real skill ceiling** in each domain — instead of a fixed quiz with a static answer key.

It works like a technical interview: questions start at a moderate level, go deeper every time you answer well, and back off to a different domain the moment you hit a wall. No domain is "complete" after one question — your strongest areas get pushed until they actually break.

## Why not just a normal quiz

Most quizzes ask a fixed set of questions at a fixed difficulty and give you a score out of N. That tells you almost nothing about where your *actual* edge is. This skill instead:

- Starts around a moderate difficulty in each domain (networking, Linux, security/exploitation, backend, databases, cloud, DevOps, web protocols, mobile, system design, etc.)
- **Escalates** difficulty in a domain after a strong answer
- **Gives one retry** on a miss, then locks in that domain's ceiling and moves to another domain
- **Re-opens a domain** if you later mention real evidence (a GitHub project, a competition result) that contradicts the earlier ceiling
- Ends with an honest **results table + a prioritized study roadmap**, not just a score

## How to use it

1. Copy `SKILL.md` from this repo.
2. Drop it into your Claude skills folder (or wherever your Claude setup loads custom skills from), or paste its contents as a custom instruction / system prompt if you're using a plain chat interface.
3. Ask Claude something like: *"Test my IT knowledge"* or *"Quiz me and find my gaps."*
4. Answer honestly — "I don't know" is treated as useful data, not failure. That's the whole point: finding the real edge, not confirming what you already know.

## What you get at the end

- A **results table**: domain → level reached → one-line evidence for that level
- A **roadmap**: what to study first, ordered by what actually matters for your stated goals (a job path, a project, a cert)
- A plain-language **narrative**: honest strengths, honest gaps, and what to do about them

## Known limitations

- Grading happens live, by the model, against no fixed answer key — so borderline answers can be graded a bit inconsistently between runs.
- Difficulty calibration ("level 3" vs "level 7") is relative and somewhat subjective, not a standardized scale.
- It's only as good as the questions it generates — it can occasionally misjudge how hard a question actually is for a given domain.
- Works best in a reasonably long conversation; very short sessions won't find a real ceiling in more than one or two domains.

## Credit

Built interactively with Claude (Anthropic), based on a real test session.
