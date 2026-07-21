# Logo assets

`docs.json` points at these paths:

- `logo/logo.png` — used in the LIGHT theme (black glyph on transparent).
- `logo/logo-inverted.png` — used in the DARK theme (white glyph on transparent, sharp-negated
  from `logo.png` so the letter is readable on `#0e1114`-style Mintlify dark backgrounds).
- `logo/favicon.png` — browser tab favicon (same source as `logo.png`).
- `logo/og-image.jpg` — social share card (referenced by `seo.metatags.og:image`; not wired yet).

Source: `web/public/genuse.png` (243×290 RGBA). The two variants here were copied + inverted from
that master. If the launchpad logo changes, refresh the master first, then re-run:

```bash
cp web/public/genuse.png docs/mintlify/logo/logo.png
cp web/public/genuse.png docs/mintlify/logo/favicon.png
node -e 'require("sharp")("web/public/genuse.png").ensureAlpha().negate({alpha:false}).toFile("docs/mintlify/logo/logo-inverted.png")'
```
