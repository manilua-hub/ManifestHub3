# Archive — Legacy Data Files

> ⚠️ **DEPRECATED — DO NOT USE IN NEW PROJECTS.**
>
> These files are historical artifacts from the legacy dataset. The website at **[maniluahub.com](https://maniluahub.com/)**
> does **not** read them. It reads manifest files directly from per-App-ID Git branches (`origin/<AppID>`).

## What's here

| File | Description | Known Issues |
| --- | --- | --- |
| `depotkeys.json` (~15 MB) | Legacy depot key cache. 288,381 entries. | 39% empty values; 7,806 entries with invalid hex characters. |
| `appaccesstokens.json` (~178 KB) | Legacy access tokens. 5,090 entries. | 4,193 IDs have no matching entry in depotkeys.json. |

## Why are they still here?

Preservation. These files were part of the historical database archive and may be useful for research purposes. They are explicitly **not** part of the active data flow.

## The active data flow

```text
maniluahub.com reads from:
  GitHub branch <AppID> → <AppID>.lua + key.vdf
```

If you need manifest files for a Steam App ID, use the website or the public API — do not parse these legacy JSON files.
