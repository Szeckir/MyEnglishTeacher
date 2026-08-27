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

1. **Before the lesson** — open Cowork with this folder and say
   `briefing`. The coach rewrites `NEXT-LESSON-BRIEFING.md` from the current
   state of `02-progress.md`.
2. **The lesson** — open a new Claude conversation, paste the briefing as the
   first message, then tap the sound-wave icon and talk for 50 minutes.
3. **After the lesson** — copy the transcript (or at minimum the final REPORT
   block) back into Cowork and say `intake`. The coach produces the four
   outputs exactly as in a normal lesson.

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
