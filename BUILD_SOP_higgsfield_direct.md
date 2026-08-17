# BUILD SOP - ship a Higgsfield static to Meta without a CDN commit

**Status: PROVEN LIVE, 17 August 2026.** This supersedes the assumption that a static must be
committed to this repo before it can become an ad.

## The finding

`ads_creative_upload_image` requires a **publicly accessible URL** and fetches the bytes itself with
no authentication. Higgsfield already publishes every completed generation to a public CloudFront
origin:

    https://d8j0ntlcm91z4.cloudfront.net/user_<userid>/hf_<YYYYMMDD>_<HHMMSS>_<generation_id>.png

That URL satisfies Meta's requirement directly. **No repo commit, no base64, no credential and no
local file transfer are needed to turn a Higgsfield generation into a Meta ad image.**

### Proof of the round trip

| Step | Value |
|---|---|
| Higgsfield generation | `5d6fec71-0c40-4aec-8cfc-305ad9dd6a1e` (13 Aug, nano_banana_2, 4:5, 1k) |
| Public rawUrl | `hf_20260813_092941_5d6fec71-0c40-4aec-8cfc-305ad9dd6a1e.png` on the CloudFront origin above |
| `ads_creative_upload_image` | **image_hash `3deb11df477bf4f7498e95e5a5fa2d03`, status ACTIVE, 928x1152** |

## Why this matters

Between **7 and 17 August 2026 this repo received no commit**, while roughly **33 QC-passed statics**
sat on a local disk and could never become ads. File `138_Aug14_TIERB_..._BUILD_SPEC` records five
separate failed upload routes: a Composio commit needing ~150k tokens of base64, no GitHub credential
in the workspace, a Lovable presigned upload that served 403 to public, and a read-only connector.

**Every one of those routes was solving the wrong problem.** The image was already publicly hosted the
moment Higgsfield finished generating it.

## The procedure

    1. show_generations(type="image")          -> find the generation
                                                  (paginate with `cursor`; it is a unix timestamp,
                                                   so you can jump straight to a date)
    2. read results.rawUrl                     -> the public CloudFront URL
    3. ads_creative_upload_image(
         ad_account_id = 675245368160350,
         image_url     = <rawUrl>,
         name          = <concept_id>)         -> returns image_hash
    4. ads_create_creative(... image_hash ...) -> page_id + instagram_user_id 17841404479992472
    5. ads_create_ad(...)                      -> lands PAUSED
    6. ads_get_ad_preview(INSTAGRAM_STANDARD)  -> READ IT (QC gate)
    7. ads_activate_entity(...)

**Still mandatory, unchanged:** the QC gate at step 6, the URL law (`domain=` exact slug from
`extraSkills.ts`, non-optional `skill_name`, `utm_content=<concept_id>`), `self_ai_disclosure: OPT_IN`,
and the compliance bans.

## What this does NOT change

- **Commit the static here anyway, after shipping.** This repo remains the scoreboard and the durable
  archive; `registry.csv` is how R1/R2/R3 see each other. Higgsfield CDN URLs are an *ingest* path,
  not a system of record.
- **`winners/` stays R3-curated.**
- **Anything not generated in Higgsfield** still needs a public URL, and for those this repo is the route.

## Compliance note carried forward

The 13 August Tier B batch includes a "DENSE PROOF" variant carrying a placement band reading
`RELIANCE - TATA - WALMART - NVIDIA`. It was **not** uploaded on 17 Aug and must not be until someone
confirms Beep-certified candidates are actually placed at those companies. The creative rules ban
unverifiable claims and third-party logo walls, and that exact pattern previously drew a Meta rejection
under "Fraud, Scams, and Deceptive Practices" which killed the E03/E05/AI-Static winners.

The sibling variant with no company names (`5d6fec71`, "the score is the hero") is fully compliant and
is the one proven above.
