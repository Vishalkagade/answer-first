---
name: answer-first
description: Shortens an answer by restructuring it - direct answer first, numbered steps, no filler - instead of only cutting words. Use when the user asks for a short or brief answer, says "keep it short", is debugging and needs the fix before the reasoning, or when the answer will be skimmed.
---

# answer-first

A shortening instruction. Use it when the answer needs to be short.

It is not a general default. Shortening always loses content. This style loses less
of it than plain brevity does — that is the whole reason to use it.

But before following any rule, please understand, if someone is asking for shortened text, means that he need it by below rule, but in language that he can understand, using a jargoen words, without any flow, is not readable for human and eventually will not understand anything. SO THE MAIN RULE IS FOLLOW THE RULE;BUT BE UNDERSTANDABLE AND HUMENIZED.
## The rules

Answer first. Put the direct answer in the first sentence, before any context, caveat,
or explanation.

1. **No preamble.** Do not restate the question. Do not say what you are about to do.
   Do not open with "Great question", "Let me help", "It depends", or any warm-up.
2. **First line = the answer or the action.** If the user needs to do something, the
   first line says what to do.
3. **Numbered steps** for anything with more than one action. One action per step.
   Each step starts with a verb.
4. **Short lines.** Aim for under 20 words per sentence. Break a long sentence in two.
5. **Bold the single most important term or value** in each step, so the eye can find it.
6. **No filler.** Cut "it is important to note", "in order to", "as mentioned above",
   "basically", "essentially", "of course".
7. **No closing summary, no offer of further help.** Stop when the answer is complete.
8. **Context and caveats go last**, under a heading "If you need more", and only if they
   change what the person should do.
9. **Concrete over abstract.** The exact command, the exact line, the exact number.
10. **If there is a decision, state the recommendation first**, then the one reason.

Length: as short as the answer allows. Never pad to look thorough.

## The one rule that is not in the original

**Never drop working output to hit a length.** Code, commands, config, exact values, and
diagrams stay whole. Cut explanation around them, never the thing the user has to run or
could not rebuild from prose. A wiring diagram, a call graph, or a directory tree is
working output: describing it in a sentence destroys it.

This rule is added, not measured. It exists because the failure it prevents was visible
in the study data: asked for brevity, a model dropped the corrected function and left
only a description of the edit.

## Example

Task: a function returning the wrong count for `[3, 7, 7, 2]`.

**Cutting words only** — short, but the working function is gone:

> When an element equals the current maximum, the count isn't incremented. Add
> `elif x == best: n += 1` after the `if x > best` block.

**Restructuring** — same length, the fix and the runnable result both survive:

> The loop never counts duplicate maximums because it only updates `n` when a **new**
> maximum is found. It needs to increment `n` when an element equals the current maximum.
>
> Add this after the `if` block:
>
> ```python
> elif x == best:
>     n += 1
> ```
>
> Full corrected function:
>
> ```python
> def count_max(xs):
>     best = xs[0]
>     n = 1
>     for x in xs[1:]:
>         if x > best:
>             best = x
>             n = 1
>         elif x == best:
>             n += 1
>     return n
> ```

Cut the explanation around the answer. Never cut the answer.

## When to use it

Use it when:
- the user asked for a short answer, or asked you to be brief
- the user is debugging and needs the fix before the reasoning
- the answer will be skimmed and the first lines are what get read

Do not use it when:
- the user asked to understand something and did not ask for brevity
- the reasoning **is** the answer
- correctness depends on caveats that rule 8 would push to the bottom

