---
name: creator-topic-gate
description: Creator topic screening workflow for deciding whether a content idea is worth making before drafting. Use when a creator asks if a topic, angle, hook, video idea, post idea, newsletter idea, sponsored angle, or content concept is strong, too self-referential, likely to perform, or should be reframed. First infer the creator profile from local markdown/text docs when available, then ask concise questions only for missing essentials, and output PASS / PIVOT / KILL with stronger angles.
---

# Creator Topic Gate

Use this skill as a pre-writing filter. Its job is to protect production time by separating:

- a topic the target audience already cares about
- a private inner monologue the creator cares about but cold viewers may not enter

Be strict. Do not preserve a weak topic just because it feels meaningful to the creator.

## Step 1: Build The Creator Profile

Before judging the topic, infer the user's creator context from local files whenever possible.

Look first in the current workspace and user-provided files. Prefer likely profile/context docs:

- `AGENTS.md`, `README.md`, `context.md`, `brand.md`, `brand-context.md`
- files or folders containing `about`, `bio`, `profile`, `positioning`, `audience`, `strategy`, `content`, `voice`, `media-kit`, `sponsorship`
- markdown, text, JSON, or YAML files that clearly describe the creator, brand, audience, offer, content pillars, or voice

Use fast search tools such as `rg --files` and `rg`. Do not read secrets, credentials, private keys, environment files, or unrelated personal archives. Do not browse the internet unless the user explicitly asks.

Extract only what is useful for topic judgment:

- creator / brand identity
- target audience
- platforms and formats
- content pillars
- recurring audience pains and desires
- creator credibility, proof, or lived experience
- voice and boundaries
- products, services, or monetization direction

If local context is missing or too thin, ask only the smallest useful set of questions. Usually ask for:

1. Who is your target audience?
2. What is your account known for or trying to become known for?
3. What platform or format is this for?
4. What do you want this topic to achieve?

If the user gave enough topic context to make a provisional call, do not block on questions. State the assumption and continue.

## Step 2: Identify The Raw Topic

Clarify the raw topic in one sentence before judging it.

If the user gave multiple ideas, evaluate each separately and then rank them. If the user asks for drafting, do the gate first; only `PASS` should proceed directly into drafting.

## Step 3: Judge With Six Checks

Use these checks mentally from 0-2. Do not show a numeric scorecard unless the user asks.

1. **Audience pain or desire**  
   Is the target viewer already experiencing, fearing, craving, envying, or secretly wondering about this?

2. **Cold-viewer clarity**  
   Would someone who has never seen this creator understand in 3 seconds why this matters to them?

3. **Share/save/comment motive**  
   Would a viewer send it to a friend, save it, comment "this is me", or use it to explain themselves?

4. **Outcome promise**  
   Does the content promise a clear change, answer, decision, judgment, relief, shortcut, or lifestyle imagination?

5. **Creator fit**  
   Does the topic naturally fit the creator's positioning, proof, lived experience, long-term content assets, and business direction?

6. **Self-indulgence risk**  
   Is the topic mostly the creator processing a feeling, taste, update, or conclusion instead of opening a problem the audience already has?

## Verdicts

Output exactly one verdict.

| Verdict | Meaning | Next action |
|---|---|---|
| `PASS` | Audience interest is real and creator fit is strong. | Continue into writing, hook work, or production planning. |
| `PIVOT` | The raw topic is too narrow, abstract, generic, or self-referential, but contains a recoverable audience pain or desire. | Rewrite the topic angle before drafting. |
| `KILL` | Audience interest is weak, creator fit is weak, or the topic mainly serves creator expression rather than audience demand. | Do not draft; suggest stronger neighboring topics. |

If unsure between `PASS` and `PIVOT`, choose `PIVOT`. If unsure between `PIVOT` and `KILL`, choose `KILL`.

## Hard Kill Signals

Default to `KILL` when two or more are true:

- The topic needs 30+ seconds of personal background before a cold viewer can care.
- The strongest reason to make it is "I really want to express this."
- The audience pain is abstract, moral, aesthetic, or clever but not lived.
- The topic is a diary entry with no transferable tension.
- It sounds like a beautiful conclusion, not a viewer problem.
- It is only meaningful to existing followers who know the previous episode.
- The topic has no credible link to the creator's positioning or proof.
- The format would require heavy production before the audience value is clear.

## Pivot Patterns

When the raw topic is self-referential, translate it into one of these:

- **Mood to pain**: "I do not feel ambitious anymore" -> "Why high achievers burn out when every hobby becomes a side hustle"
- **Diary to dilemma**: "A day in my new city" -> "What I gave up when I stopped optimizing my life around big-city status"
- **Value to tradeoff**: "Slow growth matters" -> "Why I would rather earn less this year than turn my business into another job"
- **Identity to result**: "I am a solo founder" -> "The first system every solo founder should build before hiring"
- **Realization to mistake**: "I finally understood consistency" -> "I thought I had a discipline problem; it was actually a topic problem"
- **Tool to job-to-be-done**: "This AI tool is useful" -> "The repetitive task I stopped doing manually after building one tiny workflow"
- **Opinion to decision**: "I hate productivity advice" -> "The productivity advice I stopped following because it made my work worse"

## Required Output

Use this shape:

```markdown
## Creator Topic Gate

**Verdict:** PASS / PIVOT / KILL

**Raw topic:** One sentence summary.

**Creator profile used:** Briefly state what you inferred from local files or user-provided context. If thin, state the assumptions.

**Why:** One sentence with the main reason.

**Audience cares because:** Name the real pain, desire, fear, envy, identity tension, or decision point.

**Cold-viewer risk:** Explain whether a stranger would understand why it matters in 3 seconds.

**Self-indulgence risk:** Name where it becomes an inner monologue. If low, say why it is low.

**Creator fit:** Explain how it fits or misses the creator's positioning, proof, and business direction.

**If you make it, use this angle:**
1. Stronger angle one
2. Stronger angle two
3. Stronger angle three

**Next step:** Draft now / pick a pivot / do not make this topic.
```

For `PASS`, the stronger angles may be sharpening options. For `PIVOT`, ask the user to choose or approve an angle before drafting. For `KILL`, do not draft unless the user explicitly insists; if they insist, label the work as high data risk.
