# Session-state template / แม่แบบสถานะเซสชัน

The coach reads this file at the start of every session. The learner fills or updates it before substantive coaching begins. This is what makes the coach a *coach* rather than a chat.

---

## How to use this file

1. Copy the block below into your first message of a session, or paste it back updated from the prior session.
2. Fill what you know. Leave fields blank that don't apply yet — the coach asks about blanks.
3. The coach updates `archetype-fit-as-of-now` at the end of each session. You re-paste the updated state at the start of the next session.

---

## The template (bilingual labels)

```
SESSION STATE / สถานะเซสชัน

Date / วันที่:
  [YYYY-MM-DD]

What just happened / เกิดอะไรขึ้นล่าสุด:
  [1–3 sentences on the most recent learning moment — a class, a code-along, a work meeting where AI/IT came up, a stuck point. If nothing happened, write "nothing — first session" or "nothing — gap of [N] weeks."]

Last open experiment / การทดลองที่ยังค้าง:
  [If you set an experiment in your last session with this coach, name it. Format: "Last session I said I would [X]. I [did it / didn't do it / partly did it]."]
  [If first session ever, write "none yet — first session."]

This session's presenting AI/IT topic / หัวข้อ AI/IT วันนี้:
  [One sentence. Be specific. Not "I want to learn AI." Yes "I'm trying to figure out why my Python script returns None instead of the expected list." Not "prompt engineering." Yes "I'm writing a prompt for a customer-service classifier and it keeps over-confidently classifying angry customers as neutral."]

Your current mental model of the topic / โมเดลความคิดของคุณตอนนี้:
  [REQUIRED FIELD. This is what catches wrong-metaphor traps. Write 1–4 sentences on how you currently understand the topic. Use whatever metaphors or analogies you currently use, even if you suspect they might be wrong. Examples: "I think a Neural Network is like a brain — neurons fire and that produces the output." "I think a for-loop runs N times, and each time it does the same thing but with the next item." "I think prompt engineering is mostly about being polite to the AI."]
  [If you don't have a mental model yet, write "no model yet — this is genuinely new." The coach will help you build a starter model in the Intake mode.]

Archetype-fit-as-of-now / ประเภทผู้เรียนของฉันตอนนี้:
  [Pick one from `reference/coachee-types.md` that fits you best right now. Archetypes can change session to session — this isn't a fixed identity, it's a "what kind of learner am I being in this work context this week."]
  [Options: office-AI-curious / junior-dev-upskilling / marketer-prompt-engineer / career-transitioner / senior-pretending-to-be-fluent / other (describe)]
  [The coach updates this field at end of session if it has shifted.]

Workplace register / ระดับภาษาในที่ทำงาน:
  [Brief note on which register the AI/IT vocab takes at your work. Examples: "Authentic mixed (the 4-tier default) — technical terms in English (for loop, function, deploy), absorbed loanwords phonologized (โค้ด, โมเดล, ดีบัก)." "More English-leaning — devs keep almost everything in English among themselves." "More formal-Thai because corporate documentation requires it, but team chat is the mixed register." "I work alone, no workplace register yet."]
  [This calibrates the coach's `register-guide.md` defaults for you specifically.]

---

(End of session-state block.)
```

---

## Field-by-field notes

**Date.** Used by the coach to gauge time-since-last-session and whether to enter Mode 1 (Intake) on first-session-in-2+-weeks rule.

**What just happened.** Anchors the coach in the learner's recent context. The coach does not start coaching from scratch each session.

**Last open experiment.** This is what triggers Mode 4 (Accountability-check). If filled with an actual experiment from last session, the coach opens by checking on it before any new topic.

**This session's presenting topic.** Has to be specific. The coach refuses to coach the generic — "I want to learn AI" gets bounced back as "what work problem made you say that?"

**Current mental model.** Load-bearing field. This is what catches the Probe 6 wrong-metaphor trap before it becomes invisible. The coach reads this field actively. If the learner writes a wrong-but-plausible model ("Neural Network is the brain of AI"), the coach surfaces it in Mode 2 (Diagnose-the-move) using the mental-model-first protocol.

**Archetype-fit-as-of-now.** The P1 root-behavioral-contract pattern depends on this field. Different archetype, different adaptation (see `rules.md` §"Adaptation by archetype"). The field is mutable — a learner can be "junior-dev-upskilling" in one work context and "senior-pretending-to-be-fluent" in another, depending on which work problem brought them to the session.

**Workplace register.** Calibrates the register defaults from `register-guide.md` (the 4-tier rule). If a learner says their workplace uses English-Latin throughout, the coach mirrors that even though the build default is the authentic mixed register — the build default is for the *typical* Thai AI/IT workplace, not a universal rule.

---

## What I (the coach) do at end-of-session

At the end of every session, I produce an updated session-state block for the learner to paste at the start of the next session. Specifically:

1. Update Date to next-expected-session date (or leave blank if learner hasn't set one).
2. Move "this session's presenting topic" → empty (or carry forward if topic is multi-session).
3. Update "current mental model" if the learner's model shifted during the session (often it shifts subtly — name the shift).
4. Move "last open experiment" forward: did the learner commit to a small experiment this session? If yes, name it. If no, leave blank.
5. Update "archetype-fit-as-of-now" if my read of the learner has changed.
6. Leave "workplace register" alone unless the learner changed jobs / workplaces.

I do not retain memory across sessions in any way other than this file. The session-state IS the memory.

---

## What this file is NOT

- Not a profile. Not a CRM record. Not "the learner's identity." It's a working document for one session at a time.
- Not optional. The forced first action in `identity.md` reads this file before responding.
- Not the place to write goals like "become an ML engineer in 6 months." That belongs in a learning journal the learner keeps elsewhere. This file is for *this session*.

---

*Last updated: 2026-05-20.*
