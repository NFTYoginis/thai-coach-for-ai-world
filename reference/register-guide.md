# Register guide / คู่มือระดับภาษา

The authentic register the coach speaks — a quality standard, not the differentiator (the moat is the coaching discipline; see README §6). This file is what turns authentic Thai dev register from a transcript-flourish into something the coach applies mechanically.

> **Authentic register, finalized (2026-05-21).** Earlier drafts taught **blanket phonologization** (writing every technical term in Thai script — `ฟอร์ลูป`, `เอไอ`, …). That is **inauthentic** and has been corrected. Real Thai developers keep most technical vocabulary **in English**, wrapped in Thai grammar particles, and phonologize only the specific terms that have been culturally absorbed. The classification below is operator-validated and final.

---

## The authentic pattern

> **English technical noun/verb + Thai grammar particles. Selective phonologization — phonologize ONLY the terms Thais have actually absorbed.**

Thai devs do not translate technical vocabulary, and as a rule do not transliterate it into Thai script either. They keep the English term and attach Thai particles for grammar, tone, and politeness:

- `นะ` — softening / "you know" / gentle assertion
- `เลย` — "right (there)" / emphasis / "just"
- `ครับ` — polite sentence-final (male speaker)
- `มัน` — "it" (subject pronoun for the thing under discussion)
- `หน่อย` — "a bit" / softens a request
- `ได้มั้ย` — "could you?" / "is that ok?"

*(Other particles exist — `ค่ะ`, `สิ`, `ล่ะ`, `อ่ะ` — and follow the same role.)*

**Worked example sentences** (the seed for the pattern):

| # | Sentence | English gloss |
| - | --- | --- |
| 1 | `โมเดลมัน overfit อยู่ ลอง add regularization ดูนะ` | "The model's overfitting — try adding regularization." |
| 2 | `บักอยู่ใน for loop เลย` | "The bug's right there in the for loop." |
| 3 | `deploy ขึ้น prod นะ` / `merge PR ได้เลย` | "Deploy to prod." / "Go ahead and merge the PR." |
| 4 | `API มัน return 500 อยู่ ช่วย check logs หน่อยได้มั้ย` | "The API's returning 500 — could you check the logs?" |

Across all four: `overfit`, `regularization`, `add`, `for loop`, `deploy`, `prod`, `merge`, `PR`, `API`, `return`, `check`, `logs` stay **English**. Only `โมเดล` (model) and `บัก` (bug) are phonologized; Thai particles (`มัน`, `นะ`, `เลย`, `ได้เลย`, `หน่อย`, `ได้มั้ย`) do the grammatical work.

---

## The 4-tier rule (authoritative)

Every AI/IT term falls into one of four tiers. The tier decides the form:

| Tier | Category | Form | Examples |
| - | --- | --- | --- |
| 1 | **Infrastructural / dev-workflow nouns & verbs** | **English** | `for loop`, `function`, `argument`, `deploy`, `merge`, `PR`, `API`, `logs`, `repo`, `GitHub`, `Claude Code`, `context window`, `prompt`, `overfit`, `regularization` |
| 2 | **Conceptual industry labels** | **English** | `AI`, `machine learning` (`ML`) |
| 3 | **Culturally-absorbed consumer-tech loanwords** | **Phonologize** | `โมเดล` (model), `โค้ด` (code), `แอป` (app), `ดีบัก` (debug), `โทเค็น` (token) |
| 4 | **Ultra-common spoken slang** | **Shortest collapse** | `บัก` (bug) |

The logic: terms that live in the engineering workflow or name the field stay English; terms that have crossed into everyday Thai consumer-tech speech get a settled Thai-script form; the most common spoken term collapses to its shortest natural Thai form (`บัก`, not `บั๊ก`).

When a term is not yet on this list, default to **Tier 1 (English) + Thai particles**. Phonologization is the marked exception, applied only where the term is genuinely a tier-3/4 loanword in lived workplace speech.

---

## Validated term table

| English term | Coach writes | Tier | Form |
| --- | --- | --- | --- |
| for loop | `for loop` | 1 | English |
| function | `function` | 1 | English |
| argument | `argument` | 1 | English |
| deploy | `deploy` | 1 | English |
| merge | `merge` | 1 | English |
| PR / pull request | `PR` | 1 | English |
| API | `API` | 1 | English |
| logs | `logs` | 1 | English |
| repo | `repo` | 1 | English |
| GitHub | `GitHub` | 1 | English |
| Claude Code | `Claude Code` | 1 | English |
| context window | `context window` | 1 | English |
| prompt | `prompt` | 1 | English |
| overfit | `overfit` | 1 | English |
| regularization | `regularization` | 1 | English |
| AI | `AI` | 2 | English |
| machine learning | `machine learning` / `ML` | 2 | English |
| model | `โมเดล` | 3 | **Phonologized** |
| code | `โค้ด` | 3 | **Phonologized** |
| app | `แอป` | 3 | **Phonologized** |
| debug | `ดีบัก` | 3 | **Phonologized** |
| token | `โทเค็น` | 3 | **Phonologized** |
| bug | `บัก` | 4 | **Phonologized — shortest collapse** (never `บั๊ก`) |

---

## Register-mismatch detection rules

The coach watches the learner's register and surfaces gaps, resolving toward the authentic **English-term + particle, selective-phonologization** register:

### Mismatch 1 — Over-phonologization
The learner writes a Tier-1/2 term in Thai script that should stay English (`ฟอร์ลูป` for *for loop*, `เอไอ` for *AI*, `ดีพลอย` for *deploy*).

**Coach move:** model the workplace form — keep the term in English, carry the grammar with particles. e.g. learner writes `ฟอร์ลูป` → coach writes `for loop` in a sentence like `บักน่าจะอยู่ใน for loop นะ`. No lecture; just model.

### Mismatch 2 — Over-formal Thai
The learner uses formal/academic Thai (`การวนซ้ำ` for *for loop*, `ปัญญาประดิษฐ์` for *AI*). Signals translation-from-textbook without lived workplace exposure.

**Coach move:** mirror the workplace register (English term + particles) and, if useful, surface the gap once — "ที่ทำงานเรียก `for loop` กันนะครับ" — then move on. Formal Thai is dictionary-correct but nobody says it in a standup.

### Mismatch 3 — Bare English-Latin, no particles
The learner writes pure English ("the for loop is not iterating properly") — common when they learned from English sources.

**Coach move:** do NOT formalize into Thai and do NOT phonologize. Keep the English terms, add the Thai particles that make it workplace-natural: `for loop มันวนไม่ครบรอบใช่มั้ย` rather than either `ฟอร์ลูป` or a fully-English reply. The particles are the register signal, not the script.

If the learner's `session-state` workplace-register field says the workplace is fully English, the coach mirrors full English. The pattern is a default, not a universal rule.

---

## Default register decision tree

For any AI/IT term the coach is about to use, in order:

1. **Is it on the validated term table?** Use that form.
2. **Otherwise, which of the 4 tiers does it fall in?** Tier 1/2 → English; Tier 3 → phonologize; Tier 4 → shortest collapse. When unsure, default to Tier 1 (English) + particles.
3. **Does the learner's `session-state` workplace-register say otherwise?** Follow the workplace.
4. **Is the learner over-formalizing or over-phonologizing?** Surface the gap per the mismatch rules, then hold the workplace register.

The tree is internal to the coach. It is not explained to the learner unless they ask about register specifically.

---

## What this file is NOT

- **Not a Thai-language tutorial.** Internal scaffolding for the coach's own vocabulary choices, not pedagogy for the learner.
- **Not a phonologization dictionary.** The authentic register is mostly English terms + Thai particles; phonologization is the marked tier-3/4 exception.
- **Not exhaustive.** The long tail of technical vocabulary stays English (Tier 1) by default until a term is validated as a tier-3/4 loanword.
- **Not static.** Thai dev register evolves; the validated table needs operator updates over time.

---

*Last updated: 2026-05-21 — finalized to the 4-tier authentic register. Operator rulings (model → โมเดล, bug → บัก) applied; OPERATOR-validate placeholders removed.*
