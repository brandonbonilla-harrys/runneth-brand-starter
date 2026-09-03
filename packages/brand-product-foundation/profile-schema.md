# Brand-product profile schema

Canonical output of the foundation interview. Written to
`/agent/brain/<workspace>/brand-product-profile.json`. Downstream packages read this file to
configure themselves; they must not re-ask what is already here. Keep it strict JSON.

```json
{
  "schemaVersion": 1,
  "workspaceId": "<motion workspace id>",
  "brand": {
    "name": "",
    "oneLiner": "",
    "category": "",
    "positioning": "",
    "voice": [],
    "avoidTone": [],
    "targetMarket": "",
    "competitors": []
  },
  "products": [
    {
      "id": "<slug>",
      "code": "<internal short code or null>",
      "displayNames": [],
      "category": "",
      "formFactor": "",
      "keyFeatures": [],
      "heroBenefits": [],
      "price": "",
      "offer": "",
      "referenceImages": "<drive folder / path / url>",
      "personas": [ { "name": "", "objections": [] } ],
      "claims": {
        "allowed": [],
        "banned": [],
        "disclaimers": [],
        "comparativeAnchors": []
      }
    }
  ],
  "naming": {
    "hasConvention": false,
    "tokenStructure": "",
    "registries": [],
    "handedOffToAdNaming": false
  },
  "connections": {
    "meta": { "connected": false, "adAccount": "" },
    "reviews": { "connected": false, "platform": "" },
    "drive": { "connected": false, "folders": [] },
    "slack": { "connected": false, "channels": [] }
  },
  "measurement": {
    "primaryKpi": "",
    "attribution": "meta",
    "breakeven": ""
  },
  "delivery": {
    "defaultDestination": "",
    "timing": {},
    "formatPrefs": []
  }
}
```

## Per-product doc

Each product also gets a readable `/agent/brain/<workspace>/products/<id>.md` mirroring the
product entry above, for skills that want prose (ad-gen fidelity notes, claims guard, briefs).

## Consumption rules for downstream packages

- Read `brand-product-profile.json` first. If it is missing, tell the person to run Brand &
  Product Foundation, and offer to trigger it.
- Never hardcode products, claims, naming, or channels; pull them from the profile.
- Treat `claims.banned` and `disclaimers` as hard guards in any generated copy.
- When a product's `referenceImages` are needed for ad-gen, use only that product's images.
