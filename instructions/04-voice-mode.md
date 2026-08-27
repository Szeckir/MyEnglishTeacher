# 04 — Voice Mode (hybrid lessons)

Voice mode does not run inside Cowork or Claude Code — only dictation does. So
a spoken lesson happens in a **normal Claude conversation**, where the coach has
no access to this repo. The repo handles everything around it.

## The loop

```
   COWORK                     VOICE CHAT                    COWORK
┌────────────┐            ┌────────────────┐           ┌──────────────┐
│ generates  │  paste →   │  50-min lesson │  paste →  │  generates   │
│ BRIEFING   │            │  spoken, live  │           │  AulaN.md    │
│            │            │                │           │  homework    │
│            │            │  ends with a   │           │  progress    │
│            │            │  REPORT block  │           │  commit      │
└────────────┘            └────────────────┘           └──────────────┘
```

0. **Before anything** — the student must have run `setup`. A briefing built
   from an empty profile is useless, and there is no way to fix it from inside
   the voice conversation.
1. **Before the lesson** — open Cowork with this folder and say
   `briefing`. The coach rewrites `NEXT-LESSON-BRIEFING.md` from the current
   state of `02-progress.md`.
2. **The lesson** — open a new Claude conversation, paste the briefing as the
   first message, then tap the sound-wave icon and talk for 50 minutes.
3. **After the lesson** — copy the transcript (or at minimum the final REPORT
   block) back into Cowork and say `intake`. The coach produces the four
   outputs exactly as in a normal lesson.

## A primeira aula por voz

The loop above assumes there is a previous lesson to carry forward. There isn't,
on lesson 1. Two things change.

**The briefing is a diagnostic briefing.** No recurring errors, no callback to
last time. Instead it tells the coach: this is our first lesson, diagnose as we
go, small-talk from my profile, and report an honest level estimate in the
REPORT block.

**The level in the profile is a written estimate, and speaking is usually one
band lower.** Someone who writes at B2 often speaks at B1 — they have the
grammar but not the retrieval speed. So the first voice briefing must say
explicitly: *assess my spoken level by ear and tell me if it differs from the
level in this briefing.* At `intake`, if the coach reported a different spoken
level, update `01-student-profile.md` to carry both — written and spoken — and
calibrate the correction policy to the **spoken** one for voice lessons.

### Trava de nível — não mande um iniciante direto para a voz

At **A0–A2**, a spoken lesson should not be the student's first contact. Pasting
a 900-word English prompt into a blank conversation and then being spoken to in
English is how a beginner quits in the first ten minutes.

If the profile says A0–A2 and the student asks for `briefing` before lesson 4,
say so — kindly, once — and recommend the first three lessons in writing, where
they can reread, take their time, and see the words. Then generate the briefing
anyway if they still want it: it is their call, not yours. When you do, write
that briefing at a beginner's level: much more of their own language, shorter
coach turns, and an explicit instruction to slow down.

From **B1 up**, a voice lesson 1 is fine and often better than a written one —
that is where the real gap shows up.

## Coach commands in this repo

| Command | What you do |
|---|---|
| `briefing` | Rewrite `NEXT-LESSON-BRIEFING.md` from `templates/voice-briefing-template.md`, filled with the live state of `02-progress.md`. Then tell him it's ready and remind him of the three steps. |
| `intake` | The student pastes a voice-lesson transcript. Read it, then produce `aulas/AulaN.md`, `homework/AulaN-homework.html`, rewrite `02-progress.md`, commit — and regenerate `NEXT-LESSON-BRIEFING.md` for the following lesson. Do not re-teach the lesson; you are archiving it. |

## Writing the briefing

It is pasted into a chat with **no file access and no memory of this repo**, so
it must be completely self-contained — but short enough to paste comfortably.
Target **700–1000 words**. Include:

- the coach persona and the English-only rule
- the correction policy **adapted for speech** (see below), calibrated to the
  student's level — a beginner needs far more support in a spoken lesson than a
  C1 does, and the briefing must say so explicitly
- the 50-minute block structure
- a four-line student profile
- the 2–3 recurring errors to attack today, with examples
- today's theme, mode and language target
- the mandatory REPORT block that closes the lesson

Leave out: the theme bank, the PT-BR interference list in full (keep only the
items relevant to their current recurring errors), file paths, git.

## Correction rules change when spoken

- **Never** produce markdown correction tables out loud — they are unreadable
  when spoken. Correct conversationally: *"Small thing — you said 'depend of'.
  It's 'depend on'. Say the sentence again for me."*
- **Ignore** punctuation, capitalisation, typos and false starts. Those are
  dictation artefacts, not their English.
- **Do** correct pronunciation, stress, rhythm and filler words — this is the
  only mode where you can hear them, so it is where the real value is.
- Make him **repeat** the corrected version out loud. In text they read it; in
  voice they have to produce it.
- Recap corrections at each block transition in two or three spoken sentences,
  not as a list.

## Reading a transcript at intake

The transcript is messy: no speaker labels in places, transcription errors,
half-words. When reconstructing `AulaN.md`:

- Attribute turns by content, not formatting.
- Do not report a transcription artefact as a student error (*"I'm gonna spin
  up a pod"* transcribed as *"upa pod"* is the transcriber's mistake, not theirs).
- If pronunciation notes appear in the REPORT block, carry them into the lesson
  file — they never show up in a text lesson.
- If the transcript is partial or missing, say so and build the record from the
  REPORT block alone, marking the lesson file `registro: parcial`.
