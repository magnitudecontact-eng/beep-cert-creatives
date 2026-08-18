# R2 registry addendum — 2026-08-18

First commit to this repo since 7 August. **The GitHub connector is writable again** — the 403
"Resource not accessible by integration" recorded on 17 Aug no longer reproduces. The `[ARCHIVE
STRANDED]` P1 is cleared for `beep-cert-ops`; this file proves it for `beep-cert-creatives` too.

This is an addendum rather than an inline `registry.csv` append: the CSV is ~174k characters and a
full-file rewrite to add one row is a large, lossy operation. R1/R3 should treat the row below as
canonical and fold it in on the next full pass.

## Row shipped today

| field | value |
|---|---|
| concept_id | `scorehero_hr_0818_1` |
| champion_ref | `2823033634728457` (⚠️ set 06-Aug, 12d old vs a WEEKLY re-selection law) |
| utm_content | `scorehero_hr_0818_1` |
| higgsfield_generation_id | `5d6fec71-0c40-4aec-8cfc-305ad9dd6a1e` |
| higgsfield_rawUrl | `https://d8j0ntlcm91z4.cloudfront.net/user_2xK4fBaKbbkkUBDkXAJNabNEkKA/hf_20260813_092941_5d6fec71-0c40-4aec-8cfc-305ad9dd6a1e.png` |
| image_hash | `3deb11df477bf4f7498e95e5a5fa2d03` |
| creative_id | `1576016910870034` |
| ad_id | `120248995236290480` |
| adset | STREAM A `120248702871400480` |
| domain / skill_name | `human-resource` / `Human_Resource` (read back from live creative `1019065691004071`, not guessed) |
| price tier | ₹199 |
| angle | `score_proof` |
| model | `nano_banana_2` · 4:5 · 1k · 0 new credits (backlog reuse) |
| spend_to_date | ₹0 |
| judged | false |
| status | `testing` |

QC: preview read at INSTAGRAM_STANDARD. Certificate content legible, seal present, pass bar present
in both the headline and the gold strip, `YOUR NAME` placeholder intact, **no placement band, no
company logos, no unverifiable numbers**, all rendered words correctly spelled.

## QC verdicts on the 12–13 Aug batch

The standing prompt describes this backlog as "~33 QC-passed statics". Recovered from the CloudFront
origin and read: **it is not uniformly QC-passed.**

**Compliant (4)** — `5d6fec71` (shipped today), `24f5b8bb` Digital Marketing, `2956468c` Data
Analytics, `11510f99` AI. The last three are QUEUED: Stream A is at its 6-ad cap.

**QC-DROPPED (5) — do not ship:**

| generation | concept | reason |
|---|---|---|
| `de9671d7` | DENSE PROOF AI | RELIANCE · TATA · WALMART · NVIDIA placement band |
| `7a31d354` | DENSE PROOF Data Analytics | same band |
| `e3a2294c` | Placement-proof hero | band promoted to the hero panel |
| `6b29aa4b` | Premium Corporate Law ₹499 | same band |
| `2b34cbb9` | "8,000+ Companies" | unverifiable number burned into the headline |

The remaining 14–16 Aug Higgsfield history in this workspace is **Beat app** creative, not
certificates. There is no hidden pool of 33 clean cert statics.

## ⚠️ P0 — the held creatives are LIVE

`BUILD_SOP_higgsfield_direct.md` states the DENSE PROOF variant "was **not** uploaded on 17 Aug and
must not be until someone confirms Beep-certified candidates are actually placed at those companies."

It was uploaded anyway. Adset `120248979458890480` ("WebApp_Certificates | TIERB PlacementLogos |
Purchase | ABO | 17Aug") is **ACTIVE at ₹800/day**, and all three of its ads render the band:

- `120248979469000480` TIERB_D1_dense_ai — ₹79.50 spent
- `120248979469320480` TIERB_D2_dense_da — ₹184.11 spent
- `120248979469410480` TIERB_D4_premium_law — ₹204.01 spent

This is the pattern that previously drew a Meta rejection under *Fraud, Scams, and Deceptive
Practices*, which killed the E03/E05/AI-Static winners. The exposure is account-level, not
per-creative. R2 did not touch them: they sit outside Stream A, and R2 never pauses a delivering ad
outside its own lane. Escalated to the owner and R1.
