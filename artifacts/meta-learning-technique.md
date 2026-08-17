# Learning things properly with an AI, on purpose

This is a method for using an AI to *understand* something, rather than to avoid
understanding it. It costs nothing, it needs no special software, and it works
for any subject — a programming framework, contract law, statistics, a language,
the codebase you just inherited.

It comes with a companion file, [`primer-roadmap-template.md`](./primer-roadmap-template.md),
which is the thing you actually copy and fill in. This document explains why the
method is shaped the way it is, because the shape is the whole point and it is
easy to break by accident.

You do not need to have attended the talk this came from.

## The problem it solves

In January 2026 Anthropic published a randomised controlled trial of developers
learning with and without AI assistance. The AI-assisted group scored **17%
lower** on mastery quizzes taken minutes after finishing their work — on their
own work. Roughly two letter grades. The largest gap was in debugging, which is
precisely the skill you need at the moment things go wrong.

The interesting part is the exception. Not everyone in the AI group did badly.
The people who used it for *conceptual inquiry* — asking why something worked,
asking for explanations, arguing with the answers — scored as well as the people
who had no AI at all. Same tool, same amount of time, opposite outcome. What
separated them was not talent. It was what they asked for.

That finding tells you which group you want to be in. It says nothing about how
to get there, and "ask better questions" is not a method. This is a method.

## The inversion

Almost everyone's instinct is the same: *ask the AI to write me a summary of the
topic, then read the summary.* It feels efficient. It produces a document
quickly, and the document is usually decent.

It also does very little, because reading a good explanation is not what makes
you understand something. Writing one is. When you summarise a topic yourself
you find out exactly where your understanding is thin, because the thin parts
are the ones you cannot write down. Outsourcing that step outsources the
learning and leaves you with a file.

So this method does the reverse. **Nothing is written up front.** The AI teaches
you in conversation first, and the document is produced at the *end*, as a
record of what you actually came to understand — including the parts you got
wrong on the way.

The document is a byproduct of learning, not a substitute for it.

## The mechanism that makes it work

An inversion alone is just advice, and advice gets skipped when you are busy.
The reason this holds up under pressure is a single structural rule:

> **Writing the document is a prerequisite for moving to the next topic.**

Not encouraged. Required. The AI is instructed to refuse to advance until the
write-up exists. That matters because summarising what you just learned is the
step that produces the learning *and* the step everybody skips when they are in
a hurry — which is always. Making it a gate means the valuable step is the one
you cannot quietly drop.

Everything else in the method exists to serve that gate.

## How a session actually goes

You keep **one file** — the roadmap. It lists what you are trying to learn,
broken into topics ordered so that each one builds on the last, and it carries a
status column reading either `⬜ Not started` or `✅ Covered`. That file is the
entire system. There is no app.

You open a conversation, point the AI at that file, and say *begin*. It reads
the roadmap, finds the first topic that is not yet covered, and teaches it — in
conversation, back and forth, with you interrupting as much as you like. Nothing
is written yet.

When it has finished explaining, it asks you comprehension questions. This is
where most attempts go wrong, so the instruction is explicit: it must **check
your answers**, not politely accept them. An AI's default social behaviour is to
agree with you, and an agreeable tutor is useless. Then it asks what *you* are
still unsure about, and answers that too, properly, before moving on.

Only then does it write the topic document. And only after the document exists
does it update the roadmap's status column and offer to continue.

The next session — tomorrow, or in three weeks — starts by reading the same
roadmap and picking up exactly where you stopped. That is why the status lives
in the file rather than in your head or in a chat history you will lose.

## The detail that matters most

Of everything here, this is the instruction I would least want you to drop:

> The document must reflect not just the planned material but **any clarifying
> questions and discussions that arose during the session — these often surface
> the most important nuances.**

The questions you asked are the most valuable thing produced in the whole
session, because they are the precise shape of what *you* did not understand. A
generic explainer cannot contain them. A summary written from the syllabus
cannot contain them. Only a document written from the actual conversation can.

This is what makes the output yours rather than a worse version of a textbook.
Six months later, the passage that will save you is almost always the one that
started as a confused question at the time.

## Writing rules worth enforcing

The template carries a short set of rules about *how* the topic documents get
written, and they are there to stop the AI producing reference material when
you asked for an explanation. The two that do the most work: start with the
problem before introducing the concept, so the reader feels the need for an idea
before meeting it; and build from the simplest version, show where it breaks,
then introduce the thing that fixes it.

There is also a rule against bullet-point dumps — if three or more bullets pile
up, they get converted to prose. Bullets let an explanation skip the connective
tissue between ideas, which is where the understanding actually lives. This
document follows its own rule, which is why it reads the way it does.

## What to do when it goes wrong

The most common failure is an AI that advances without really testing you,
because agreeing is easier than correcting. If you notice you are being waved
through, say so directly and ask it to mark your last answer honestly. The
second most common failure is skipping the write-up "just this once" to keep
momentum. That is the one thing in this method that is not optional; the moment
the gate becomes advisory, you are back to reading summaries.

If a topic turns out to be much larger than the roadmap assumed, split it into
two rows rather than letting one session sprawl. The ordering is the other half
of the value — a curriculum where each topic genuinely builds on the last is
what lets you learn something hard without repeatedly bouncing off it.

## Where the idea came from

The method was arrived at sideways. I built it to teach myself a technique
called ACE — a system that lets *AI agents* improve over time by capturing what
they learn while working, curating it, and feeding it back in, so that the next
task starts smarter than the last.

Partway through, the joke became obvious: I had built a personal version of the
same loop in order to learn the original. Do the work, reflect on what changed,
write it down, come back better. One loop pointed at an agent, one pointed at a
person, and the influence ran backwards from the thing being studied to the way
of studying it.

That is not a coincidence so much as a hint. Anything that improves — a person,
a team, a piece of software — is running some version of that loop, and the step
almost everyone skips is writing the lesson down.

## Credits

The mastery study is Anthropic's, published January 2026:
<https://www.anthropic.com/research/AI-assistance-coding-skills>.

The framing of why any of this matters — that when intelligence is abundant,
what differentiates people is their relationship to mental effort — is David
Brooks', in *The People Who Will Thrive in the AI Age*, The Atlantic, 28 June
2026: <https://www.theatlantic.com/ideas/2026/06/ai-open-ai-anthropic/687689/>.

The method itself is just a shape. Take it and change it.
