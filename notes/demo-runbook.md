# Demo Runbook

Four live demos, 15 minutes of a ~70 minute talk. **There is no screenshot
fallback — that was a deliberate choice**, so the mitigation is this document
plus rehearsing against a clock.

Every cap below is hard. When it is up you stop, mid-sentence if necessary. The
2026-03-03 talk ran long using only screenshots; the caps are the whole defence.

| Act | Demo | Runs on | Cap |
|---|---|---|---|
| 0 — Hook | Talk a dashboard into existence | react-loop-demo on the cluster | **5:00** |
| 3 — The loop | Replay the debug panel, ambiguous prompt | same app | **3:00** |
| 5 — Show and tell | Point an agent at the vault | laptop, local | **4:00** |
| 6 — Local models | Ollama on the Windows box | RDP to Windows | **3:00** |

## FILL IN before the day

- Dashboard app URL: `FILL IN`
- Windows box hostname / IP for RDP: `FILL IN`
- Ollama model to use: `FILL IN` — pull it well in advance, it is gigabytes
- **The vault query (Act 5): `FILL IN`** — see that section; this one is not optional

---

## Screen sharing

Open **two windows**: the deck, and the presenter view at `/presenter/`. Share
the **deck window specifically — never the whole screen or desktop**, or the
room sees your notes. On HDMI, use extended display rather than mirroring.

Present from `npm run dev` locally rather than from GitHub Pages. Sync between
the presenter view and the deck is only reliable on the dev server, and running
locally means the slides do not depend on the network — which the demos are
already spending.

`d` toggles dark/light if the room is brighter than expected. `o` is the slide
overview. The deck is 52 slides; the diagrams are 16, 37 and 44.

---

## Pre-flight

**The week before**

- Pull the Ollama model onto the Windows box. Run it once so it works.
- Confirm the dashboard app is deployed and reachable, with a working key behind it.
- Decide and rehearse the vault query.

**Thirty minutes before**

- Dashboard app open in a tab, loaded, with one throwaway prompt already run so
  the first cold request is not happening in front of people.
- **RDP session to the Windows box established and left open.** Do not plan to
  connect during the talk. Disable sleep and screen lock on that machine, and set
  its display scaling large enough to read from the back of the room.
- Ollama already answering on that box — run one query so the model is loaded into
  memory. A cold model load in front of an audience will blow the 3:00 cap on its
  own.
- Agent open in the vault directory, at the right folder, with any private notes
  you do not want on screen closed.
- Deck running locally, presenter view open, timer visible.

**Two minutes before**

- Notifications off. Slack, Mail, Messages, calendar alerts.
- Browser tabs closed down to only what the demos need.
- Water. All four demos involve talking while something else is happening.

---

## Act 0 — Talk a dashboard into existence · cap 5:00

**Open cold.** No introduction, no agenda slide. Open the app and start typing.
Debug panel on from the first keystroke, and it stays on.

**Say almost nothing.** Every explanation spent here is one you cannot spend in
Act 3, and the whole design of the talk is that they watch the machinery before
they have any vocabulary for it. They should see structured text scrolling past
that they cannot read yet.

Prompts, in this order — the ambiguous one **last**:

1. `Chart my grocery and dining spending by month as a bar chart`
2. `Add a table of transactions over $200 this year, biggest first`
3. `Make the chart section green and move it to the top`
4. `Show my checking balance` ← two checking accounts exist, so it should stop and ask

That fourth one is the moment. When it asks which account you meant, pause and
let the room sit with it. Do not say "notice how it asked." They will notice.

**Exit line:** "I'm going to leave that there, and I'm not going to explain any
of it yet." → next slide.

**If it fails:** say so plainly — "that's live, and live things break" — and move
to the next slide. The talk survives it; Act 3 replays this material anyway, so
lean harder on the replay. Do not debug in front of the room.

---

## Act 3 — Replay the debug panel · cap 3:00

Same app, same panel, but now they have the vocabulary. Narrate against the
actual words as they scroll: **there is the request, there is the tool call,
there is the result coming back, and now round again.**

Then the ambiguous prompt: `Show my checking balance`

What should happen is a tool call whose only job is to ask the user a question.
Draw that out — the honest move was not to produce an answer, it was to stop.
Asking a question is an action like any other.

**If it guesses instead of asking:** do not hide it. Say so, and say why — it is a
probabilistic system and this is exactly the failure mode we manage. That is a
more honest talk than one where the demo always works.

**Exit line:** "That's the loop. Everything from here is a consequence of it."

---

## Act 5 — Ask the vault · cap 4:00

⚠️ **The query is chosen and rehearsed in advance.** The vault holds work
material and personal notes. Do not free-range, and **do not take a suggested
query from the room** — say plainly that there is private material in here and
that is exactly why the query is prepared. That refusal is itself a good moment:
it demonstrates the judgment the talk is arguing for.

Pick a query that reads across *several* notes rather than retrieving one, so the
demo shows synthesis rather than search. Something spanning years is ideal,
because the point is reading more at once than a person can hold.

Show the shape: it searches, reads a few files, follows a reference into another
note, and answers with citations back to where it found things. Point at the loop
while it runs — that is a tool call, that is an observation, the same twelve lines
from Act 3 pointed at a folder of text files.

**The beat to land:** it is not doing anything clever. It is reading, quickly,
across more material than I can hold in my head. The intelligence is ordinary.
The corpus is what is rare.

**Exit line:** "None of that was written for an AI. That's the whole point."

---

## Act 6 — Ollama on the Windows box · cap 3:00

⚠️ **Do not claim to be offline.** The RDP session needs the network, so "watch
me pull the wifi" is not available and would be a lie. The slide was rewritten
for this: the claim is **ownership, not disconnection**.

Say where you are — this is a desktop in my house, and I am looking at its screen
from here. The model on it is a file I downloaded, and it is doing the work on
that machine, not in anybody's data centre.

Ask it something ordinary. Let it be slower than the room expects and **do not
apologise for the wait** — a machine in a spare room doing this at all is the
point.

While it generates: nothing I type leaves hardware I own. For anything genuinely
confidential — medical, financial, legal, family — that is the whole case, and it
does not require trusting anyone's privacy policy. It also cannot be discontinued,
price-raised, or quietly changed, which is a different kind of safety from privacy.

**Do not oversell the quality.** It is visibly weaker than the frontier models,
and pretending otherwise costs credibility — the next slide depends on you having
been honest about it.

**If RDP has dropped or the box has slept:** do not reconnect live. Skip to the
next slide and make the argument verbally; it is a four-slide act and the other
three carry it.

**Exit line:** "Weaker than the big ones, and for some jobs that's fine — which is
the next slide."

---

## After the demos

Nothing to reset for Act 7 except your own attention. The closing slide has a URL
on it, so make sure the deck window is the one being shared and not a leftover RDP
session.
