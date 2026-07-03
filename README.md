# creator-topic-gate

**Before you write the post, check if the topic is worth making.**

This skill helps creators screen content ideas before drafting. It first tries to understand the creator from local docs such as `README.md`, `context.md`, `brand.md`, audience notes, positioning docs, or media-kit files. If it cannot find enough context, it asks a few concise questions.

Then it judges the topic with a simple verdict:

| Verdict | Meaning |
|---|---|
| `PASS` | The audience already cares and the topic fits the creator. |
| `PIVOT` | The idea has something real, but the angle is too narrow, abstract, generic, or self-referential. |
| `KILL` | The idea is mostly creator expression, weak audience demand, or poor creator fit. |

## What It Checks

- Audience pain or desire
- Cold-viewer clarity
- Share/save/comment motive
- Outcome promise
- Creator fit
- Self-indulgence risk

## Example Prompts

```text
Use Creator Topic Gate to judge this idea: "Why I stopped chasing productivity."
```

```text
I want to make a RedNote post about my first month as a solo founder. Is this worth doing?
```

```text
Screen these 5 newsletter ideas and tell me which one I should write first.
```

## Install

After publishing this repository, install it as a plugin/skill package using your Codex or Claude plugin workflow.
