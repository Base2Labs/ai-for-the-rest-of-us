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

## The setup

Nothing runs on the laptop. Two of the four demos are elsewhere on the network.

| What | Where | Notes |
|---|---|---|
| Dashboard app | <https://reactloop.basetwolabs.com> | Public, behind Cloudflare. **HTTP Basic auth.** |
| Windows box | `10.1.1.239` over RDP | LAN address — reached via the **Tailscale subnet route** |
| Local model | `gemma4:26b` | 25.8B params, **~17 GB**. `llama3.2` (~1.9 GB) is on the box as a fallback |
| Vault | `~/Vaults/Work/2 Areas/AI` | 11 notes, ~5.8k words. **Scoped deliberately — see Act 5** |

**The vault query is chosen and tested** — see the Act 5 section. Everything in
this runbook has now been verified rather than assumed.

### Measured, not guessed

- `gemma4:26b` **cold load: ~21s.** Warm: **0.5s**, then ~38 tokens/sec.
  Twenty-one seconds is 12% of the 3:00 cap spent watching nothing — this is why
  warming the model is a pre-flight step and not a nicety.
- The dashboard app returns **401 until authenticated**. Basic auth, so no SSO
  redirect or one-time code to fight — but the browser will throw a credentials
  dialog if the session is not already established.

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
overview.

**54 slides.** Type a number and press Enter to jump straight to it.

| Slide | What |
|---:|---|
| **2** | 🔴 Act 0 demo — "This would normally take a developer weeks" |
| 3 | "What just happened?" — the beat, then Act 1 |
| 16 | ReAct loop diagram |
| **22** | 🔴 Act 3 demo — replay the panel |
| 39 | Learning-loop diagram (personal) |
| **43** | 🔴 Act 5 demo — ask the vault |
| 46 | Learning-loop diagram (agent) — same shape as 39, on purpose |
| **49** | 🔴 Act 6 demo — Ollama over RDP |
| 54 | Close, with the artifacts URL on screen |

---

## Pre-flight

**The week before**

- Confirm `gemma4:26b` still answers on the Windows box: `curl http://10.1.1.239:11434/api/tags`
- Confirm <https://reactloop.basetwolabs.com> loads and you have the Basic auth credentials to hand.
- Confirm the LangGraph notes are still in `~/Vaults/Work/2 Areas/AI` and the roadmap status table still shows unfinished topics — the query's answer depends on it.

**Thirty minutes before**

- **Tailscale up on the presenting machine, and the `10.1.1.0/24` route actually
  accepted.** Run `tailscale status`. A client can report connected while
  silently not taking the subnet route, and that failure looks exactly like the
  Windows box being down.
- **Dashboard app open and already authenticated**, in the exact window you will
  present from. Run one throwaway prompt so the first request is not cold in
  front of people. Do **not** open a fresh or private window during the talk —
  it will prompt for credentials on screen, and autofill in front of a room is
  how a password ends up on a projector.
- **RDP session to `10.1.1.239` established and left open.** Do not plan to
  connect during the talk. Disable sleep and screen lock on that machine, and set
  its display scaling large enough to read from the back of the room.
- **Warm the model** — send one query so `gemma4:26b` is resident. Cold it costs
  ~21 seconds of a 180-second cap; warm it starts in half a second.
- **Agent open in `~/Vaults/Work/2 Areas/AI`** — check the path on screen before you start. Opening it a level up is the one mistake that puts private material in front of the room.
- Deck running locally, presenter view open, timer visible.

**Two minutes before**

- Notifications off. Slack, Mail, Messages, calendar alerts.
- Browser tabs closed down to only what the demos need.
- Water. All four demos involve talking while something else is happening.

---

## Act 0 — Talk a dashboard into existence · cap 5:00

**Say the two lines on the slide, then open the app.** No introduction, no agenda.
Debug panel on from the first keystroke, and it stays on.

> *This would normally take a developer weeks. And I'm not going to write any code.*

Those lines exist because a cold open only works if the room can tell what is
remarkable, and most of this room cannot — they have never had to know that
software normally takes weeks and costs money. Without that yardstick the best
five minutes in the talk lands on nothing. The lines give away the price, not the
mechanism; Act 3 still keeps the mystery.

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

**Open the agent in `~/Vaults/Work/2 Areas/AI` — not the vault root.** This is a
hard requirement, not a preference. See "why this folder" below.

**The query:**

> *Read across my LangGraph notes — what did I actually learn, where did I stop,
> and what did I get stuck on along the way?*

Tested end to end: **~90 seconds**, comfortably inside the cap.

It has to read the roadmap plus six topic documents to answer, so it is genuine
synthesis rather than retrieval. The answer is concrete and checkable — six
topics covered, four never started, and the sticking points are recorded in the
documents themselves.

**The beat to land, and it is the best one in the act:** those documents were
produced *by the technique from twenty minutes ago*. Act 4 taught the method;
this is an agent reading the artefacts that method created. The demo proves the
technique works and demonstrates documentation-as-context in the same move.

Point at the loop while it runs — that is a tool call, that is an observation,
the same twelve lines from Act 3 aimed at a folder of text files.

**It is not doing anything clever.** It is reading, quickly, across more material
than I can hold in my head. The intelligence is ordinary. The corpus is what is
rare.

**Exit line:** "None of that was written for an AI. That's the whole point."

### Why this folder, and why not the obvious ones

⚠️ **Do not point this at the vault root, and do not take a query from the room.**
Say plainly that there is private material in here and that is exactly why the
query is prepared. That refusal is a good moment — it demonstrates the judgment
the talk is arguing for.

Two candidates were tested and rejected:

- **Project retrospectives.** The completion sections are unfilled template
  checklists. The only reflection in any of them is *"Simple project, nothing
  really to reflect on."* There is nothing to synthesise, so the demo would have
  quietly produced something thin while you talked over it.
- **Weekly reviews.** 106 notes and by far the best answer — meetings recur in 25
  separate weeks, one project dominated 12, and you wrote *"mostly a lot of
  context switching last week"*, which is the exact problem the PKM was built to
  solve. **But the same corpus contains layoffs, a merger, medical information, a
  vendor called a shitshow, a colleague dispute and a dozen internal project
  names.** Not projectable. Revisit only if you want to read the synthesis aloud
  without showing the screen.

## Act 6 — Ollama on the Windows box · cap 3:00

⚠️ **Do not claim to be offline.** The RDP session needs the network, so "watch
me pull the wifi" is not available and would be a lie. The slide was rewritten
for this: the claim is **ownership, not disconnection**.

Say where you are — this is a desktop in my house, and I am looking at its screen
from here. The model on it is a file I downloaded — **seventeen gigabytes, about
twenty-six billion numbers** — and it is doing the work on that machine, not in
anybody's data centre. The size is worth saying out loud; it makes "a file you
download" concrete in a way that "a local model" never does.

Ask it something ordinary. Let it be slower than the room expects and **do not
apologise for the wait** — a machine in a spare room doing this at all is the
point.

While it generates: nothing I type leaves hardware I own. For anything genuinely
confidential — medical, financial, legal, family — that is the whole case, and it
does not require trusting anyone's privacy policy. It also cannot be discontinued,
price-raised, or quietly changed, which is a different kind of safety from privacy.

**Be accurate about the quality — this was tested.** At 26B it answers an ordinary
question about as well as a frontier model would, so do **not** claim it looks
visibly weaker; on this kind of question it doesn't, and the room can see that.
The honest line is that the gap opens on genuinely hard reasoning, not on
everyday questions — which is exactly what sets up the next slide.

**If RDP has dropped or the box has slept:** do not reconnect live. Skip to the
next slide and make the argument verbally; it is a four-slide act and the other
three carry it.

**If the model is crawling:** `llama3.2` is on the same box at ~1.9 GB and will
answer far faster. Weaker, but "two gigabytes, on a desktop in my house" is the
same argument at a smaller number — and a fast weak answer beats a slow one you
have to apologise for.

**Exit line:** "Weaker than the big ones, and for some jobs that's fine — which is
the next slide."

---

## After the demos

Nothing to reset for Act 7 except your own attention. The closing slide has a URL
on it, so make sure the deck window is the one being shared and not a leftover RDP
session.
