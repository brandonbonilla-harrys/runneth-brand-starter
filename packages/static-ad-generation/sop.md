# Static Ad Generation SOP

Generate a static image ad for one of the brand's products. Engine: **Gemini reference-image
flow** (`gemini-3-pro-image` via `GEMINI_API_KEY`). All product specifics come from the
brand-product profile, never hardcoded.

## Prerequisites

- `brand-product-profile.json` present. Pick the target product from it.
- The product's canonical reference images exist at the profile's `referenceImages` location.
- `GEMINI_API_KEY` connected. `ffmpeg` available for aspect enforcement.

## 1. Load context

- Read the target product entry: reference images, key features, hero benefits, personas,
  price/offer, and `claims` (allowed / banned / disclaimers / comparativeAnchors).
- Read any template library the brand has (see `template-library-engine`); otherwise use a clean
  editorial layout. Pick a hook/angle to fill (coverage gap or a proven winner reformatted).

## 2. Build the prompt (reference-images-only)

- Attach the product's canonical reference image(s) as the fidelity source.
- The text prompt must **not describe the product** and must **not include a negative/"do not
  render" list**. Fidelity comes only from the reference images; instruct the model to render the
  product exactly as shown in the attached photos.
- The prompt may cover only: layout/structure reference, scene/background, on-image copy
  (verbatim), staging (product large + grounded), aspect ratio, and claim safety on the copy.
- Aspect: request 4x5 in the prompt text (`aspectRatio: 4:5`).

## 3. Claims + placeholder guard (hard gate)

- Every on-image claim must be in the product's `claims.allowed`; none may hit `claims.banned`.
- Apply required `disclaimers` and any `comparativeAnchors` (e.g. a "vs prior product"
  disclaimer) when a comparative claim is used.
- No placeholder text, lorem, or unreadable copy. If a claim can't be made safely, change the
  copy, don't ship it.

## 4. Generate

- Call `gemini-3-pro-image` with the reference images + prompt. Save the raw output.

## 5. Enforce aspect (mandatory)

- Always upscale to exactly 1080x1350 (4x5):
  `ffmpeg -i {out} -vf scale=1080:1350:flags=lanczos {out} -y -hide_banner -loglevel error`.

## 6. Fidelity review

- Compare the render against the reference image(s). Product geometry, labels, and form must
  match exactly. Strong figure/ground contrast; no product-on-flat-fill + text. If fidelity
  fails, regenerate; do not present it as approval-ready.

## 7. Asset ID + naming

- Assign the next per-brand asset ID from the brand's ledger (a simple incrementing scheme;
  source of truth is the reference-images directory, not a counter that can drift).
- Build the ad name from the brand's naming convention (profile `naming` / `ad-naming` package).

## 8. HTML brief + ledger

- Produce a self-contained HTML brief (image base64-embedded, download button, product, asset ID,
  hook, template/mechanic/stage tags, rationale, ad name). Save to `./artifacts/`.
- Copy the final image into the brand's reference/asset store and update the ledger + any
  learning notes.

## 9. Delivery

- Deliver the HTML brief as an openable link. In Slack, post the strategy summary + a labeled
  link to the brief (no raw file paths). Follow the brand's delivery/format prefs from the profile.

## Guards

- Reference-images-only; never describe the product or add a negative prompt.
- Claims/disclaimers are hard gates. Aspect enforcement is mandatory on every generation.
- Never present a low-fidelity render as approval-ready.
