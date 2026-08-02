# Prompt Bank — refreshed 2026-08-02 (R3 scheduled Sunday run)

Weights live in `beep-cert-ops/intelligence/angle-weights.json` (as_of 2026-08-02).
Domains come from `beep-cert-ops/intelligence/skill-economics.json` target_share — **never** encode a domain bias here.
Codex is binding: dark statics, one mechanic line, honest claims, no video/UGC, no price in a cold hook.

> **All performance figures below are META-ATTRIBUTED, UNVERIFIED AT BANK.** utm_content coverage 1.6%; Razorpay session-blocked for a 5th cycle.

---

## 1. shark_tank_trust — weight 0.34 (winning angle of the week)
**Evidence:** 19 ads, ₹100,295, Meta ROAS 1.140, 479 purchases. Best large family on the board.
**Reference:** `03 SharkTrust Finance | STAG | Fresh 28Jul` (1.53 on ₹8,181/60) · `02 SharkTrust HR | STAG` (1.33 on ₹5,290/30) · `03 SharkTrust AI | Fresh 25Jul` (1.84 on ₹513/5)
**Prompt seed:** Dark static. Shark-Tank-backed trust mark, top-left. Line 1 names the domain outcome. Line 2 is the mechanic: "Verified score, dated certificate, 10 minutes." Domain token visible. No price.
**Domains:** HR, Cyber, AI, Finance (per target_share).

## 2. score_proof — weight 0.14
**Evidence:** 1.371 on ₹581/3 — best per-rupee return of any family; promoted from new_bet.
**Reference:** `03 ScoreProof HR NEWBET | Fresh 26Jul`
**Prompt seed:** Dark static. The score band is the hero — a visible graded result, not a claim. Line 1: "You scored 78%." Line 2: "Now it is on a certificate recruiters can verify."
**Needs:** ≥₹2,000 to confirm.

## 3. resume_proof — weight 0.14
**Evidence:** 1.296 on ₹539/1, **plus 133/887 feedback rows** ("Resume looks empty compared to peers", 21.0% of specific-pain respondents). Underfunded, not underperforming.
**Reference:** `09 ResumeProof DigitalMarketing | Fresh 25Jul`
**Prompt seed:** Dark static, split composition. Left: an empty resume block. Right: the same block with a dated, verifiable credential. Line: "The difference is one line. Verified."

## 4. wachat_selected — weight 0.13 (DOWN-WEIGHTED)
**Evidence:** 0.925 on ₹22,123/98 across 7 ads. **Was 1.51 on the quiz-LP; it has decayed under scale.** Keep funded, no longer a lead angle.
**Prompt seed:** Selection/shortlist framing without the WhatsApp chrome — the chrome is what fatigued. Lead with the selection decision, not the channel.

## 5. interview_outcome — weight 0.13 (HELD despite 0.907)
**Evidence:** 0.907 on ₹23,541/96. Held because the demand is the strongest in the dataset — **168/887 feedback rows** ("Not getting interview calls despite applying") is now the **#1 named pain**, ahead of resume_empty. `03 InterviewShortlist Finance` burned ₹1,213 at 0.00: the angle is right, the execution is wrong.
**Fix:** current executions state the OUTCOME without a MECHANIC. See new bet `interview_callback_mechanic`.

## 6. authority_newdomain — weight 0.07
**Evidence:** 0.927 on ₹10,617/31, but `Certified Accountant | Authority | 27Jul` returned **3.24 on ₹461/4** — the best ROAS on the board.
**Prompt seed:** Professional register, authority seal motif. "<Role> without the certification is just experience." / "Verified credential, 10 minutes, dated."
**Critical:** run these SKUs at **₹199**, not ₹299/₹499. The domains convert at 9.6–16.7% at the paywall; the ₹299/₹499 lanes die at LPV→Checkout (5.6–7.6% vs 14.3% blended).

## 7. skills_current — weight 0.05 (token)
**Evidence:** 0.282 on ₹1,235/2 — breached its own kill criterion. Demand is real (150/887) but the creative execution failed. Any re-run needs a **new mechanic, not a re-skin**.

---

## New bets (R2 exploration quota) — kill: <1.0 banked @ ₹300/48h
1. **career_gap_explainer** — 43/887 name a career gap; +48 more want to switch fields (91 total, 14.4% of specific-pain). Zero concepts in the bank address it.
   Seed: "A 9-month gap on your resume." / "This is what you put next to it."
2. **interview_callback_mechanic** — name the ATS/skill-verification screen that rejects before a human reads.
   Seed: "400 applications. 0 calls." / "The screen rejects you before a human reads it. Verified skills clear the screen."
3. **authority_professional_sku** — authority angle on legal/accounting SKUs at ₹199.

## Banned (do not generate)
- Price-led cold hooks — `05 Python Risk-Free 199` 0.00 on ₹499 this week; 11th consecutive failure.
- Video / creator-UGC for cold direct-to-checkout — `VideoCreativeTest 29July` 0.618 on ₹1,031, paused day 1.
- Direct-checkout deep-link concepts (0.23–0.70 every attempt).
- Generic outcome hooks with no domain token — `EastZone | GetAICertified` 0.00 on ₹358.
