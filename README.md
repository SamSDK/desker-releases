# desker-releases

Public release manifest for [Desker](https://samsdk.github.io)'s in-app, opt-in update
checker. This repo holds no application source code — that lives in the private
`SamSDK/desker` repo. The only file that matters here is `latest.json`, fetched directly
(unauthenticated) at:

```
https://raw.githubusercontent.com/SamSDK/desker-releases/main/latest.json
```

## Format

```json
{
  "version": "1.67.0",
  "url": "https://example.com/download/DeskerSetup-1.67.0.exe",
  "notes": "What changed in this release."
}
```

- `version` — semver (`major.minor.patch`). The checker only notifies when this is
  *strictly newer* than the running build.
- `url` — must be `https://`; anything else is treated as absent (no Download button).
- `notes` — short, shown in the update banner.

`url` and `notes` are left empty until a real signed installer exists to link to.
