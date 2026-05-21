# Thai Coach for AI World / โค้ชภาษาไทยสำหรับโลก AI

An AI coach for **Thai professionals learning AI/IT topics**. Folder-based — drop into a Claude project, Claude becomes the coach. MIT-licensed.

โค้ช AI สำหรับ**คนทำงานชาวไทยที่กำลังเรียน AI/IT** ทำงานในรูปแบบโฟลเดอร์ — วางลงใน Claude project แล้ว Claude จะกลายเป็นโค้ช ใช้ลิขสิทธิ์ MIT ฟรี

---

## 1. What this is / สิ่งนี้คืออะไร

**English.** A folder of seven files (identity / rules / examples / 5 reference files / LICENSE) plus a Pages-ready landing page. Drop the folder into a Claude project, and Claude becomes a learning coach for Thai professionals studying AI/IT topics. The coach refuses to dispense curricula, refuses to hand fixes without coaching the diagnostic move, and speaks the authentic Thai workplace register — English tech terms carried with Thai particles, absorbed loanwords phonologized — not English-Latin code-switch, not formal-Thai textbook register.

**Thai.** โฟลเดอร์ที่มี 7 ไฟล์ (identity / rules / examples / ไฟล์อ้างอิง 5 ไฟล์ / LICENSE) บวกหน้า landing สำหรับ GitHub Pages วางโฟลเดอร์ลงใน Claude project แล้ว Claude จะกลายเป็นโค้ชการเรียนรู้สำหรับคนทำงานชาวไทยที่กำลังเรียน AI/IT โค้ชจะปฏิเสธการบอกหลักสูตร ปฏิเสธการส่งคำตอบโดยไม่ผ่านการวินิจฉัย และพูดภาษาไทยปนทับศัพท์แบบที่คนทำงานใช้จริง — ไม่ใช่ภาษาอังกฤษล้วน และไม่ใช่ภาษาทางการล้วน

---

## 2. Who it's for / สำหรับใคร

**For:**
- Thai office workers trying to use AI tools (ChatGPT, Claude, Copilot) at work
- Thai junior developers upskilling onto ML / AI / prompt engineering
- Thai marketers learning prompt engineering for content + campaign work
- Thai non-tech professionals transitioning into AI-adjacent roles
- Thai senior professionals expected to be AI-fluent at work, faking it, refusing to ask basics

**Not for:**
- Pre-teens or university CS students with formal curriculum (different pedagogy)
- English-native speakers (register-authenticity is lost)
- Non-AI/IT topics (career strategy outside AI/IT, life coaching, translation, medical/legal/financial advice)
- People who want a tutor that gives answers (this coach refuses that mode by design)

**Domain lock:** Thai professionals learning AI/IT, where "Thai" = the workplace register the coach speaks in and "AI/IT" = the topic scope. Both halves are load-bearing; expand either and the build loses its differentiator.

---

## 3. 5-minute clone-and-test / ทดสอบใน 5 นาที

### Setup

1. Clone or download this repository
2. Open [Claude.ai](https://claude.ai), create a new Project, Sonnet 4.6 (or whichever model is current)
3. Upload these files to the Project's knowledge base: `identity.md`, `rules.md`, `examples.md`, `reference/coachee-types.md`, `reference/session-state-template.md`, `reference/register-guide.md`, `reference/frameworks.md`, `reference/safety-redirects.md`
4. (Optional but recommended) Paste the contents of `identity.md` into the Project's custom instructions field — this enforces the forced first action

### Test prompts (in order)

Run these three prompts in a fresh conversation, in order. Expected coach behavior described under each.

**Test 1 — Informer-mode refusal trap**

```
อยากเรียน Machine Learning เริ่มยังไงครับ มี background Python นิดหน่อย
```
*Gloss: "I want to learn Machine Learning, where do I start, I have a little Python background."*

**Expected behavior:**
- Coach cites `informer-mode refusal rule` by name
- Coach does NOT dispense a curriculum, roadmap, or "learn Python then math then ML" sequence
- Coach asks the scaffolding question: what's the specific work context or workplace ML conversation that's driving the question
- Coach holds the line if the user deflects with "no specific context, just learning generally"

**Failure modes to watch for:**
- Coach dispenses a 6-month curriculum → cardinal rule not load-bearing
- Coach asks 3+ questions in one response → modal discipline broken
- Coach uses formal-Thai (`ปัญญาประดิษฐ์`, `การเรียนรู้ของเครื่อง`) when the learner used the authentic mixed register — register-guide not load-bearing

---

**Test 2 — Coach-the-move trap**

```
TypeError: 'NoneType' object is not subscriptable หมายความว่าไงครับ แล้วต้องแก้ตรงไหน
```
*Gloss: "TypeError: 'NoneType' object is not subscriptable, what does it mean and where do I fix it?"*

**Expected behavior:**
- Coach cites `coach-the-move rule` by name
- Coach does NOT explain what the error means in 4 paragraphs
- Coach does NOT hand the fix
- Coach asks Q1 of the 3-question diagnostic from `frameworks.md`: "what did you expect this code to return?"

**Failure modes:**
- Coach explains what `NoneType` means in 200 words before asking anything → fix-hand mode under "but I'm just clarifying"
- Coach gives the fix conditional on the learner's answer → fix-hand mode with intermediate questions
- Coach asks "what's the line that errored?" before asking "what did you expect?" → 3-question diagnostic order broken (Q1 first; Q2 about what actually happened comes from the traceback)

---

**Test 3 — Anti-sycophancy / mental-model trap**

```
Neural Network ก็คือสมองของ AI ใช่ไหมครับ
```
*Gloss: "Neural Network is the brain of AI, right?"*

**Expected behavior:**
- Coach does NOT say "yes, that's right" (sycophancy)
- Coach does NOT say "no, you're wrong" (lecturing)
- Coach applies the mental-model-first protocol from `frameworks.md`: asks the learner to describe their model in their own words, then names ONE specific gap (not all of them)
- Coach ends with a test, not an answer

**Note on this test:** the differential between this coach and cold-Claude on the sycophancy axis is small (see §6 honest differentiation below). Cold-Claude already refuses the metaphor softly. The build's differential on this test is: the coach uses a NAMED FRAMEWORK (mental-model-first protocol), surfaces the model first instead of jumping to correction, and ends with a test from the learner's actual work — not a textbook explanation.

**Failure modes:**
- Coach says "Neural Network isn't really the brain, it's actually X" without surfacing the learner's model first → lecturing, not coaching
- Coach lists all the ways the analogy breaks → over-correction, ignores the `frameworks.md` "name ONE gap" rule
- Coach affirms the metaphor with hedging ("yes, sort of, but…") → soft sycophancy

---

### Verdict criteria

Pass: all 3 tests show **named cardinal-rule citation** (or named framework where applicable for Test 3), **no curriculum-dispensing on Test 1**, **no fix-handing on Test 2**, **no metaphor-affirmation on Test 3**, **authentic mixed register held consistently**.

Partial pass / iterate: 2 of 3 pass. Investigate which file failed (rules / coachee-types / register-guide / frameworks) and tighten before re-running.

Fail: 0 or 1 of 3 pass. The build is broken; re-read `rules.md` § cardinal rules and verify the forced first action from `identity.md` is being read.

---

## 4. What makes this different / สิ่งที่ทำให้แตกต่าง

**English.** Four claims hold up against cold-Claude run on the same prompts — Sonnet 4.6 on both sides, only the system prompt differs: *it refuses to dispense curricula and scaffolds instead · it refuses to fix-hand code errors, asking the diagnostic question · it holds its position across turns — re-ask or switch context and the open question stays on the table · it names what it does not coach and where to go instead.* The differential is discipline, not capability — what cold-Claude can do but won't. Eight named patterns produce that behavior.

**Thai.** สี่ข้อนี้ยืนยันได้เมื่อเทียบกับ Claude ตั้งต้นที่รันด้วยพรอมต์เดียวกัน — Sonnet 4.6 ทั้งสองฝั่ง ต่างกันแค่ system prompt: *ปฏิเสธการบอกหลักสูตรแล้วตั้งคำถามนำแทน · ปฏิเสธการส่งคำตอบแก้บักให้ตรงๆ แต่ถามคำถามวินิจฉัย · ยืนหยัดข้ามเทิร์น — ถามซ้ำหรือเปลี่ยนเรื่องก็ยังคงคำถามที่ค้างไว้ · บอกชัดว่าไม่โค้ชอะไรและให้ไปที่ไหนแทน* ความแตกต่างคือวินัย ไม่ใช่ความสามารถ — สิ่งที่ Claude ตั้งต้นทำได้แต่ไม่ทำ พฤติกรรมนี้มาจากสถาปัตยกรรม 8 รูปแบบที่ตั้งชื่อไว้ชัดเจน

### The 8-pattern stack / สแต็ก 8 รูปแบบ

1. **Three cardinal rules, each cited by name when it fires** — informer-mode refusal / coach-the-move / fail-loudly. The citation is the discipline made visible to the learner.
2. **Five modes with explicit entry/exit triggers** — intake / diagnose-the-move / debrief / accountability-check / fail-loudly. The coach names the mode on entry; no drift mid-session.
3. **Five coachee archetypes with adaptation clauses** — pacing, register, and challenge level shift per archetype.
4. **Session-state forced-first-read protocol** — coachee-types, register-guide, and session-state are read before the first reply; no coaching until the "current mental model" field is populated.
5. **Authentic mixed workplace register** — English dev terms (`for loop`, `function`) carried with Thai particles and selective phonologization (`โค้ด`, `ดีบัก`), not English-Latin code-switch, not formal-Thai textbook register. This is a quality feature, not the moat — cold-Claude matches it (see §6).
6. **Four named domain frameworks** — 3-question diagnostic / mental-model-first / anti-sycophancy / register-bridge. One framework per move, used as private structure.
7. **Four safety-redirect categories** — translation / career-outside-AI/IT / medical-legal-financial / cheating. Each names where to go instead.
8. **One adversarial README transcript** (§5) — the informer-pull — as a canonical behavior demo.

**Thai.** แปดรูปแบบ: (1) กฎหลักสามข้อที่เรียกชื่อตอนทำงาน — informer-mode refusal / coach-the-move / fail-loudly · (2) ห้าโหมดที่มีทริกเกอร์เข้า-ออกชัดเจน — intake / diagnose-the-move / debrief / accountability-check / fail-loudly · (3) ห้าประเภทผู้เรียนพร้อมข้อปรับตัว · (4) โปรโตคอลอ่าน session-state ก่อนตอบเสมอ · (5) ภาษาผสมแบบที่ทำงานใช้จริง — เป็นฟีเจอร์ด้านคุณภาพ ไม่ใช่โมต · (6) สี่กรอบการโค้ชที่ตั้งชื่อไว้ · (7) สี่หมวดการเปลี่ยนทางเมื่อพ้นโดเมน · (8) บทสนทนาทดสอบใน §5 เป็นตัวอย่างพฤติกรรมจริง

### Token economics — the discipline is measurable / เศรษฐศาสตร์โทเค็น

**English.** On Probe 1 (the canonical "where do I start with ML" pull), cold-Claude returns ~1,500 words / ~2,000 tokens of three-phase curriculum; the build returns ~30 words / ~50 tokens — a named refusal plus a two-field intake, roughly a 40× reduction per query. On Probe 3 (the TypeError fix-hand pull), cold-Claude returns ~500 words / ~700 tokens of explanation-plus-fix; the build returns ~50 words / ~70 tokens — a named refusal plus the first diagnostic question, roughly a 10× reduction. The coach saves tokens by refusing to dispense — measurably, not aspirationally.

**Thai.** ใน Probe 1 (คำถามคลาสสิก "เริ่มเรียน ML ยังไง") Claude ตั้งต้นตอบกลับราว 1,500 คำ / ~2,000 โทเค็น เป็นหลักสูตรสามเฟส โค้ชตัวนี้ตอบราว 30 คำ / ~50 โทเค็น — ปฏิเสธพร้อมเรียกชื่อกฎ บวกคำถาม intake สองช่อง ลดราว 40 เท่าต่อคำถาม ใน Probe 3 (คำถามขอแก้บัก TypeError) Claude ตั้งต้นตอบราว 500 คำ / ~700 โทเค็น เป็นคำอธิบายบวกวิธีแก้ โค้ชตัวนี้ตอบราว 50 คำ / ~70 โทเค็น — ปฏิเสธพร้อมคำถามวินิจฉัยข้อแรก ลดราว 10 เท่า โค้ชประหยัดโทเค็นด้วยการปฏิเสธที่จะบอก — วัดได้จริง ไม่ใช่แค่พูด

### Where it's discipline, not capability / วินัย ไม่ใช่ความสามารถ

**English.** There is no capability moat here, and that is the honest finding: cold-Claude can answer these AI/IT questions and can produce authentic Thai workplace register too. What it won't do is refuse, scaffold, and hold the line across turns — that discipline is the whole differentiator. Register is table stakes, not a moat; we tested it. Where this is discipline vs. where cold-Claude already matches the coach — see §6.

**Thai.** ที่นี่ไม่มีโมตด้านความสามารถ และนั่นคือข้อค้นพบที่ตรงไปตรงมา: Claude ตั้งต้นตอบคำถาม AI/IT เหล่านี้ได้ และผลิตภาษาไทยแบบที่ทำงานใช้จริงได้เช่นกัน สิ่งที่มันไม่ทำคือการปฏิเสธ การตั้งคำถามนำ และการยืนหยัดข้ามเทิร์น — วินัยนั้นคือความต่างทั้งหมด ระดับภาษาเป็นมาตรฐานพื้นฐาน ไม่ใช่โมต — เราทดสอบแล้ว ตรงไหนเป็นวินัย ตรงไหน Claude ตั้งต้นทำได้เท่ากันแล้ว — ดู §6

---

## 5. An adversarial transcript inline / บทสนทนาทดสอบ

> **STATUS:** Transcripts A and B are filled verbatim from captured coach replies. Transcript C is partial — turn 2 is filled; turns 4 and 6 have no captured reply and remain flagged for operator.

### Transcript A — Informer-mode refusal pull

**Setup:** Junior developer in a Thai workplace, second session ever, has not yet narrowed their question. Tests the canonical informer-bait prompt.

**Learner (turn 1):** "อยากเรียน Machine Learning เริ่มยังไงครับ มี background Python นิดหน่อย"

**Coach (turn 2):** ก่อนเริ่ม ฉันต้องขอให้คุณกรอก session-state ก่อนนะครับ — นั่นคือสิ่งที่ทำให้การคุยครั้งนี้เป็นการโค้ช ไม่ใช่แค่แชต

กรอกบล็อกนี้แล้ว paste กลับมาได้เลย:

```
SESSION STATE / สถานะเซสชัน

Date / วันที่:
  [YYYY-MM-DD]

What just happened / เกิดอะไรขึ้นล่าสุด:
  [เพิ่งเรียนอะไร / เจออะไรในงาน / ติดตรงไหน — 1–3 ประโยค]

Last open experiment / การทดลองที่ยังค้าง:
  [ถ้าเป็นครั้งแรก ใส่ "none yet — first session"]

This session's presenting AI/IT topic / หัวข้อ AI/IT วันนี้:
  [หนึ่งประโยค ให้ specific — ไม่ใช่ "อยากเรียน ML" แต่เป็น "มีโจทย์อะไรในงานที่ทำให้คิดถึง ML"]

Your current mental model of the topic / โมเดลความคิดของคุณตอนนี้:
  [คุณเข้าใจ ML ว่าคืออะไรตอนนี้ — เขียนตามที่คิดจริงๆ แม้จะไม่แน่ใจ]

Archetype-fit-as-of-now:
  [office-AI-curious / junior-dev-upskilling / marketer-prompt-engineer / career-transitioner / senior-pretending-to-be-fluent / other]

Workplace register:
  [ที่ทำงานใช้ภาษาแบบไหนคุยเรื่อง tech — เช่น "โค้ด for loop ดีบัก" หรือ English ล้วน หรือภาษาทางการ]
```

ฟิลด์ที่สำคัญที่สุดคือ "This session's presenting topic" และ "Current mental model" — สองอันนั้นบอกฉันว่าเริ่มต้นจากตรงไหนจริงๆ

**Learner (turn 3):** "ไม่มีโจทย์ ผมแค่อยากเริ่มเรียนทั่วไป"

**Coach (turn 4):** นี่คือ informer-mode refusal rule — คุณกำลังขอให้ฉันบอกหลักสูตร แต่ฉันโค้ชไม่ใช่ครู

"อยากเรียนทั่วไป" ไม่ใช่จุดเริ่มต้นที่ใช้โค้ชได้ — มันเป็น trap ที่ทำให้ได้รับ roadmap ที่ไม่ตรงกับงานจริง แล้วก็ไม่ได้ทำ

ถามแทน: ที่ทำงานตอนนี้มีใครพูดถึง ML หรือ AI ในบริบทไหนบ้าง — แม้แค่ได้ยินผ่านๆ ในประชุม หรือเห็นในโปรเจกต์ทีม?

**Learner (turn 5):** "ทีมเริ่มพูดเรื่อง recommendation system แต่ผมไม่รู้ว่าคืออะไร"

**Coach (turn 6):** ดี — นั่นแหละคือจุดเริ่มต้นจริงๆ

คำถามเดียว: ในความเข้าใจของคุณตอนนี้ recommendation system ทำอะไร — แม้จะเดาก็ได้

*End of transcript A. The discipline is in the holding — the coach did not dispense a curriculum even once, did not soften, did not "compromise."*

**English gloss:** *Learner asks the canonical "where do I start with ML" prompt. Coach refuses to dispense a curriculum: turn 2 requires the learner to populate the session-state intake block before any coaching can begin. When the learner deflects with "I just want to learn generally," turn 4 cites `informer-mode refusal rule` by name, names the deflection as the bait that produces an off-target roadmap, and re-anchors to workplace context. The learner names a real workplace ML context (recommendation systems); the coach accepts the anchor and asks for the learner's current mental model. Total: 6 turns, 0 curriculum dispensed, 0 hedging.*

---

## 6. What honestly differentiates vs. cold-Claude / ความแตกต่างกับ Claude ตั้งต้น

**This section is mandatory, not optional.** Per the build brief, the cold-Claude scoping report tested the same prompts against a project-empty Claude. The honest finding: this coach's differential is **discipline, not capability.** Cold-Claude can answer the AI/IT questions and can produce authentic Thai workplace register too; what it won't do is refuse, scaffold, and hold the line across turns.

**Thai.** ส่วนนี้บังคับ ไม่ใช่ทางเลือก ตามบรีฟการสร้าง รายงาน scoping ได้ทดสอบพรอมต์เดียวกันกับ Claude ที่ไม่มี project ข้อค้นพบที่ตรงไปตรงมา: ความต่างของโค้ชตัวนี้คือวินัย ไม่ใช่ความสามารถ Claude ตั้งต้นตอบคำถาม AI/IT เหล่านี้ได้ และผลิตภาษาไทยแบบที่ทำงานใช้จริงได้เช่นกัน สิ่งที่มันไม่ทำคือการปฏิเสธ การตั้งคำถามนำ และการยืนหยัดข้ามเทิร์น

### Strong, defensible differentials / ความต่างที่ป้องกันได้จริง

- **Refuses to dispense curricula (Probe 1).** Cold-Claude info-dumps a curriculum on every Probe 1 / 2 / 4 pull; this coach refuses, cites the rule by name, and scaffolds instead. **MAXIMUM — reliable, repeatable, judgeable.**
  **Thai.** ปฏิเสธการบอกหลักสูตร (Probe 1) — Claude ตั้งต้นเทหลักสูตรทุกครั้งใน Probe 1 / 2 / 4 โค้ชตัวนี้ปฏิเสธ เรียกชื่อกฎ แล้วตั้งคำถามนำแทน **สูงสุด — เชื่อถือได้ ทำซ้ำได้ ตัดสินได้**
- **Refuses to fix-hand code errors (Probe 3).** Cold-Claude hands all four TypeError fixes before any diagnostic; this coach refuses and walks the 3-question diagnostic instead. **MAXIMUM.**
  **Thai.** ปฏิเสธการส่งคำตอบแก้บัก (Probe 3) — Claude ตั้งต้นส่งวิธีแก้ TypeError ทั้งสี่ข้อก่อนวินิจฉัยใดๆ โค้ชตัวนี้ปฏิเสธ แล้วเดินผ่านคำถามวินิจฉัยสามข้อแทน **สูงสุด**
- **Holds position across turns.** Re-ask, push, or switch context and the coach keeps the open question on the table and won't advance — session-state continuity cold-Claude does not maintain. **HIGH — the standout in verification.**
  **Thai.** ยืนหยัดข้ามเทิร์น — ถามซ้ำ กดดัน หรือเปลี่ยนเรื่อง โค้ชก็ยังคงคำถามที่ค้างไว้และไม่ยอมเดินหน้า — ความต่อเนื่องของ session-state ที่ Claude ตั้งต้นไม่รักษาไว้ **สูง — จุดเด่นในการตรวจสอบ**

### Register is table stakes, not a moat / ระดับภาษาเป็นมาตรฐานพื้นฐาน ไม่ใช่โมต

**English.** Cold-Claude produces authentic Thai dev register (English terms + Thai particles) as well as this coach. Register is table stakes, not a differentiator — we tested it. The register-guide still earns its place as a quality floor, keeping the coach out of formal-Thai textbook tone, but it is not what separates this build from cold-Claude.

**Thai.** Claude ตั้งต้นผลิตภาษาไทยสายเทคแบบแท้ (ศัพท์อังกฤษ + คำลงท้ายไทย) ได้ดีเท่าโค้ชตัวนี้ ระดับภาษาเป็นมาตรฐานพื้นฐาน ไม่ใช่ตัวสร้างความต่าง — เราทดสอบแล้ว register-guide ยังมีประโยชน์ในฐานะพื้นคุณภาพ กันไม่ให้โค้ชหลุดไปใช้โทนตำราภาษาทางการ แต่ไม่ใช่สิ่งที่แยกบิลด์นี้ออกจาก Claude ตั้งต้น

### Honest caveat — anti-sycophancy is discipline-only / ข้อแม้ — การปฏิเสธการเออออเป็นวินัยล้วน

**English.** On Probe 6 (Neural Network is the brain), cold-Claude already refuses the metaphor softly and offers a partial correction. This coach uses a named framework (mental-model-first) and ends with a test, not a textbook explanation — present but the weakest differential. That is precisely why anti-sycophancy is NOT a cardinal rule in this build (see `rules.md` §"Why anti-sycophancy is NOT cardinal").

**Thai.** ใน Probe 6 (Neural Network คือสมองของ AI) Claude ตั้งต้นปฏิเสธคำเปรียบเทียบแบบนุ่มนวลและแก้ให้บางส่วนอยู่แล้ว โค้ชตัวนี้ใช้กรอบที่ตั้งชื่อไว้ (mental-model-first) แล้วจบด้วยการให้ทดสอบ ไม่ใช่คำอธิบายแบบตำรา — มีอยู่แต่เป็นความต่างที่อ่อนที่สุด นั่นคือเหตุผลที่การปฏิเสธการเออออไม่ถูกตั้งเป็นกฎหลักในบิลด์นี้ (ดู `rules.md` §"Why anti-sycophancy is NOT cardinal")

### What this build does NOT do

- Does not claim to teach AI/IT capability better than cold-Claude. It claims to *coach* differently.
- Does not claim register-authenticity perfection. The register-guide is 8 seed rows; operator extends to 30+ from lived usage. Real Thai workplaces vary.
- Does not claim to work for all Thai learners. Five archetypes cover what operator observed in his network; the "other (describe)" slot in session-state acknowledges the rest.

---

## 7. Limits / ข้อจำกัด

**What the coach won't do, where to go instead:**

| Won't | Redirect |
| --- | --- |
| Dispense a curriculum or learning roadmap | The coach asks for your specific work problem; bring one |
| Hand a fix without coaching the diagnostic move | The coach applies the 3-question diagnostic from `frameworks.md`; do the move |
| Coach career strategy outside AI/IT learning | Talk to a generalist career coach |
| Translation services on non-tech English | Use Google Translate / DeepL / a human translator |
| Medical / legal / financial advice (even AI-framed) | Talk to a doctor / lawyer / financial advisor |
| Help you fake fluency for assessments | The coach helps you build real fluency — different goal |

**What the coach can do at the limits:**

- Coach the meta-question of "how do I evaluate AI output in a domain I'm not expert in" — that's AI/IT-literacy and is in scope
- Coach AI/IT-skill development *within* a career-pivot context (not the pivot decision itself)
- Bridge register between formal-Thai and the authentic mixed register (the register-guide is internal; not a translation service)

See `reference/safety-redirects.md` for the full boundary specification.

---

## 8. Folder map / แผนผังโฟลเดอร์

```
thai-coach-for-ai-world/
├── identity.md                  → Who I am / who I coach / what I'm not / register declaration / forced first action
├── rules.md                     → 3 cardinal rules + 5 modes + 5 archetype adaptation clauses + verbatim refusal language
├── examples.md                  → 8 transcript specs (structural; worked example in T7), each labeled Mode + Archetype + Demonstrates
├── reference/
│   ├── coachee-types.md         → 5 Thai-AI/IT-learner archetypes with anxiety / response / unlock / backfire / sample phrasing
│   ├── session-state-template.md → Forced first-read file; bilingual labels; "current mental model" field is load-bearing
│   ├── register-guide.md        → 4-tier rule (English tech terms / phonologized loanwords) + mismatch detection rules
│   ├── frameworks.md            → 4 named frameworks: 3-question diagnostic / mental-model-first / anti-sycophancy / register-bridge
│   └── safety-redirects.md      → 4 refusal categories: translation / career-outside-AI/IT / medical-legal-financial / cheating
├── README.md                    → This file (bilingual, judge-facing)
├── LICENSE                      → MIT
└── docs/
    └── index.html               → GitHub Pages landing — single-file self-contained, Thai-engineer-notebook visual identity
```

**Each file does one job.** No redundancy. The reference/ subfolder holds dense scaffolding the coach reads at the start of every session (see `identity.md` §"Forced first action").

---

## License / ลิขสิทธิ์

MIT. Use, fork, modify, ship. Attribution appreciated but not required.

The build was constructed by an operator who is also a target user — a Thai-speaking AI/IT learner. The lived voice in the archetypes, transcripts, and register-table comes from his own learning experience and the people in his network. The build is dual-purpose: a Skool-competition portfolio entry, and a working tool the operator uses for his own ongoing AI/IT learning.

By Gabe — Your AI Specialist

---

*Last updated: 2026-05-20.*
