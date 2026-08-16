---
layout: section
---

<!-- ACT 3 — THE REACT LOOP · 15 min · 11 slides · live demo cap 3:00 -->
<!-- ⭐ THE SPINE. Largest act. Everything downstream is a consequence of mechanics introduced here. -->

# The loop

---

# The reveal

Every line that scrolled past in that debug panel was one turn of the same small loop, running over and over.

---

# Reason, then act

The model thinks about what to do, does one thing, sees what happened, and goes again — that's ReAct, and it's from a 2022 paper.

---

# The whole loop is twelve lines

Ask the model; if it asked for a tool, run the tool and append the result; otherwise you're done.

<!-- code as texture — narrate, never walk line by line -->

---

# What goes in, what comes back

Side by side: the request carrying the tool descriptions, and the reply that is nothing but a function name and arguments.

<!-- the single code-as-texture slide for this act — four payloads collapsed to one -->

---

# The model never drew anything

It only emitted structured requests; ordinary deterministic code did the drawing — model proposes, harness disposes.

---

# A tool is a function with a description

Name, description, parameters — and the description is doing the real work, because that's all the model ever sees of it.

---

# Watch it decide

Same loop, panel open, a deliberately ambiguous request — so it stops and asks instead of guessing.

<!-- 🔴 LIVE · react-loop-demo · cap 3:00 -->

---

# Why there's a context limit

The loop re-sends the entire conversation every turn, so the thing you're paying for and running out of is the transcript, not the model.

---

# Why it forgets in the middle of a task

When the transcript stops fitting, something has to summarize it — and a summary is lossy by definition.

---

# The memory wall

Nothing carries over between sessions, and half the industry is building elaborate workarounds for exactly that.

---

# Everything after this is loop management

Prompts, skills, planning, sessions, scripts — every technique in the next act is a way of controlling what goes into the loop.
