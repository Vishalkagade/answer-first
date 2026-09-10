# answer-first

A Claude skill that shortens an answer by **restructuring** it rather than only cutting
words. Direct answer first, numbered steps, no filler — and never drop the code, the
command or the diagram to hit a length.

## Install

Clone straight into your skills directory:

    git clone https://github.com/Vishalkagade/answer-first.git ~/.claude/skills/answer-first

For one project instead of every project:

    git clone https://github.com/Vishalkagade/answer-first.git /path/to/project/.claude/skills/answer-first

Start a session and ask for something short. Check it loaded with `/skills`.

**Anywhere else** — another agent, a chat UI, your own app: open `SKILL.md` and paste the
rules into your system prompt.

## When to use it

Use it when the answer needs to be short: the user asked for brevity, or is debugging and
needs the fix before the reasoning, or will skim and stop after the first lines.

It is not a general default. Shortening always loses something. This loses less of it than
plain brevity does — that is the whole reason to reach for it.

Do not use it when someone asked to understand something and did not ask for brevity. If
the reasoning is the answer, compressing it throws away the deliverable.

## Why this and not "be concise"

It was measured. Across 810 generated answers on debugging, how-to and explanation tasks:
at the **same length**, this style kept **8 to 18 percentage points more of the source
facts** than a plain "be concise" instruction. All intervals excluded zero.

Both ways of shortening lose content against a full-length answer. This one loses less.

What the study could not establish, in its own words: whether the shortened answers still
*work* — whether the code runs — was never tested, and no human was involved at any point,
so nothing here is a claim about what any person understands or prefers.

## Licence

MIT. See [LICENSE](LICENSE).
