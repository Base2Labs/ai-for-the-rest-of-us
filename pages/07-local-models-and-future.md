---
layout: section
---

<!-- ACT 6 — LOCAL MODELS + THE FUTURE · 7 min · 4 slides · live demo cap 3:00 -->
<!-- Directly answers the attendee-requested topics (Ollama, future of tech). -->
<!-- Open weights is motivated here rather than listed as an attribute back in Act 2. -->
<!-- Act ends on the counterweight by design — it earns Act 7 the right to make its argument. -->

# On your own machine

---

# Open weights, plainly

- Some models are a **service you rent**. You send text away; someone else runs it.
- Some are **files you download**. Multi-gigabyte files of numbers, yours to keep.
- That is the whole distinction — and it is why running one at home is possible at all.
- Rented ones are generally stronger. Downloaded ones are private, free to run, and cannot be taken away.

<!--
Somebody asked about running these locally, so let me do the one distinction that makes it make sense.

Some models are a service. You send your text to a company, their computers do the work, you get an answer back. Everything most people use is this.

Others are published as files. Genuinely just files — several gigabytes of numbers — that you download and run on your own machine. That is what open weights means. Not open source exactly, and the licences vary, but the practical fact is: you have the file.

That is the entire reason local models exist. You cannot run a rented model at home because you were never given it.

Trade-offs are honest and simple. The rented ones are generally more capable, especially at the hard end. The downloaded ones are private — nothing leaves the room — free once you have them, work without internet, and cannot be discontinued, price-raised, or have their behaviour changed underneath you next Tuesday. For some jobs that matters more than raw capability.
-->

---

# On a machine in my house

- Not a data centre. No account, no subscription, nobody's API.
- The model is a file I downloaded. It runs on hardware I own.
- Which means nothing I type goes anywhere, and nobody can change it underneath me next Tuesday.

<!--
🔴 LIVE — Ollama on the Windows box over RDP · HARD CAP 3:00 · runbook in notes/demo-runbook.md

⚠️ Do NOT claim to be offline. The RDP session needs the network, so "watch me pull the wifi" is not available and would be a lie. The honest claim is ownership, not disconnection.

Say where you are: this is a desktop in my house, and I am looking at its screen from here. The model on it is a file I downloaded — a few gigabytes of numbers — and it is doing the work on that machine, not in anybody's data centre.

Ask it something ordinary. Let it be slower than the room expects and do not apologise for the wait; a machine in a spare room doing this at all is the point.

The argument to land while it generates: nothing I type leaves hardware I own. For anything genuinely confidential — medical, financial, legal, family — that property is the whole case, and it does not require trusting anyone's privacy policy. Worth adding that it also cannot be discontinued, price-raised, or quietly changed, which is a different kind of safety from privacy.

Be accurate about the quality. At 26B this answers an ordinary question about as well as a frontier model would, so do NOT claim it looks visibly weaker — on this kind of question it doesn't, and the room can see that. The honest line is that the gap opens on genuinely hard reasoning, not on everyday questions. Which is exactly what sets up the next slide.

Three minutes, then stop whatever is on screen.
-->

---

# When small is the right answer

- Cost, privacy, and speed all point the same way: smaller than you think.
- Frontier models for judgment and ambiguity. Small models for volume and well-specified work.
- **Best pattern going:** let the small model do it, and the big one check it.
- Keep it swappable — this changes every few months, so don't marry one.

<!--
So when is small actually right, beyond privacy.

More often than people assume. There is a reflex to reach for the most capable model for everything, and it is mostly wasted. Once a task is well specified and repetitive, a small model does it fine, faster and at a fraction of the cost — and cost stops being theoretical the moment you are running something thousands of times rather than chatting.

The pattern I keep coming back to, from an engineer at AWS who builds these systems: small model does the work, big model reviews it. You spend the expensive judgment only on judging, which is the part that needed it.

And build so you can swap. The specific best model right now will not be the best model in six months. Anyone who has hardwired themselves to one is going to have a bad time — including, and I mean this, in how you personally work. Do not get too attached.
-->

---

# The honest counterweight

- MIT: roughly **95%** of corporate generative-AI pilots deliver no measurable return.
- The ones that work were aimed at **growth**, not at cutting headcount — 2–3× more likely, per McKinsey.
- 43% of workers admit shipping AI output they suspected was wrong.
- The technology is real. Most attempts to apply it are still bad.

<!--
Before I finish, the slide that stops this being a sales pitch — and it is the honest state of things.

MIT looked at corporate generative-AI pilots and found something like ninety-five percent produced no measurable return. Ninety-five. Everything I have shown you tonight is real and I stand behind all of it, and simultaneously most organisations trying to do this are getting nothing.

That is not a contradiction, and the pattern in the failures is instructive. McKinsey found the organisations getting real value were two to three times more likely to be using it for growth — doing more, doing new things — than for efficiency, meaning doing the same things with fewer people. Aim it at subtraction, get very little. Aim it at expansion, get somewhere.

And one more, which points straight at the close: a survey found forty-three percent of workers admitted shipping AI output they suspected was wrong. Not could not tell was wrong. Suspected was wrong, and shipped it anyway.

That is not a technology failure. That is a people-under-pressure failure, and no better model fixes it.

Hold that number. It is exactly where I want to end.
-->
