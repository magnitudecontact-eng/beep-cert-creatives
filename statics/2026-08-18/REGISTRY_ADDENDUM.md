# R2 registry addendum — 2026-08-18 (rev 2)

First commits to this repo since 7 August. **The GitHub connector is writable again** — the 403
"Resource not accessible by integration" recorded on 17 Aug no longer reproduces.

Addendum rather than an inline `registry.csv` append: the CSV is ~174k characters and a full-file
rewrite to add two rows is a large, lossy operation. R1/R3 should treat the rows below as canonical
and fold them in on the next full pass.

## Rows shipped today

### 1 — `scorehero_hr_0818_1` (backlog reuse, 0 credits)

| field | value |
|---|---|
| ad_id / creative_id | `120248995236290480` / `1576016910870034` |
| image_hash | `3deb11df477bf4f7498e95e5a5fa2d03` |
| higgsfield_generation_id | `5d6fec71-0c40-4aec-8cfc-305ad9dd6a1e` |
| domain / skill_name | `human-resource` / `Human_Resource` |
| price tier / angle | ₹199 / `score_proof` |
| model | `nano_banana_2` · 4:5 · 1k · 0 new credits |
| status | `testing`, judged false, spend ₹0 |

QC PASS. Caveat: carries a rendered `Saurabh Mangrulkar / Founder and CEO` signature. §3 bans
fabricated signatures; §0 and `BUILD_SOP_higgsfield_direct.md` both name this exact generation the
fully compliant sibling. Shipped on the repo-wins rule — **flagged for a wording ruling.**

### 2 — `authority_fin_0818_1` (fresh generation, cleanest asset in the set)

| field | value |
|---|---|
| ad_id / creative_id | `120249012937530480` / `1262405622588691` |
| image_hash | `0464440402c1afe1bcde7d2f1003a458` |
| higgsfield_generation_id | `fb8d245c-90db-42d8-bae7-514d27cae43c` |
| higgsfield_rawUrl | `https://d8j0ntlcm91z4.cloudfront.net/user_2xK4fBaKbbkkUBDkXAJNabNEkKA/hf_20260818_182128_fb8d245c-90db-42d8-bae7-514d27cae43c.png` |
| reference media | `bcc8485f-596f-4ccf-82b0-6d8cfc1c0b58` (`ref_certhero_0730`) |
| champion_ref | `2823033634728457` (⚠️ 12d old vs a WEEKLY re-selection law) |
| domain / skill_name | `finance` / `Finance` (read back from live creative `830251370078468`) |
| price tier / angle | ₹199 / `authority_newdomain` |
| model | `nano_banana_2` · 4:5 · 1k · first attempt, 0 regenerations |
| status | `testing`, judged false, spend ₹0 |

QC PASS, and the reason it matters: **no signature, no person's name, no job title, no company names
or logo band, no price in the image.** Landscape black-and-gold certificate, rosette with 100%,
`YOUR NAME` placeholder, `FINANCE` in gold, `Scored 92%`, QR bottom-right, mechanic line and gold
strip both present, every word correctly spelled.

**This is the template to reuse.** The explicit forbidden-elements paragraph in the prompt is what
kept the signature and the company band out. It is reproduced verbatim in the audit JSON.

## Actions taken

**Paused — banned placement band (all 3, confirmed no longer delivering):**
`120248979469000480` D1_dense_ai ₹79.50 · `120248979469320480` D2_dense_da ₹184.11 ·
`120248979469410480` D4_premium_law ₹204.01. Total ₹467.62 spent on held creatives.

⚠️ Their parent adset `120248979458890480` is still **ACTIVE at ₹800/day** with those creatives
attached. Re-enabling any one of them puts the band back in market. Pause the adset or delete the
three creatives.

**Paused — orphaned E1 experiment:** `120248702900630480` E1 VARIANT. §0 rules E1 unreadable with
the control pruned 15 Aug. A real re-run needs BOTH arms on fresh IDs; the old control carries
₹6,577 from a different budget and coverage era and is not a clean partner.

## QC verdicts on the 12–13 Aug batch

The standing prompt calls this "~33 QC-passed statics". Recovered from the CloudFront origin and
read: **it is not uniformly QC-passed.**

**Compliant (4):** `5d6fec71` (shipped), `24f5b8bb` Digital Marketing, `2956468c` Data Analytics,
`11510f99` AI — the last three QUEUED.

**QC-DROPPED (5) — do not ship:** `de9671d7` DENSE PROOF AI, `7a31d354` DENSE PROOF Data Analytics,
`e3a2294c` placement-proof hero, `6b29aa4b` Premium Corporate Law ₹499 (all four carry the
RELIANCE · TATA · WALMART · NVIDIA band), and `2b34cbb9` ("8,000+ Companies", unverifiable).

The remaining 14–16 Aug Higgsfield history in this workspace is **Beat app** creative, not
certificates. There is no hidden pool of 33 clean cert statics.

## ⚠️ Stream A is dark — today's ships deliver nothing

Meta activity log, read directly:

- **17 Aug 18:05 IST** — the **owner** cut Stream A ₹1,200 → ₹400/day. A deliberate decision, not a
  fault. An earlier version of this file filed it as a P0 against R1; that attribution was wrong.
- **18 Aug 21:52 IST** — **Saubhagya Sharma** set the Stream A adset Active → Inactive.

All 6 Stream A ads read `status=ACTIVE` / `effective_status=ADSET_PAUSED`. Nothing delivers. The
13-Aug snapshot records the same actor darkening this same campaign 18:17–01:56 across the 12-Aug
evening peak, so this is a recurring pattern rather than a one-off.

R2 did **not** re-activate: a deliberate action by another operator, taken minutes earlier, for an
unknown reason. Re-activating would be an activation war during peak hours. Escalated instead.
