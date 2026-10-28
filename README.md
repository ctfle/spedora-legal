# saddle-legal

Public legal pages for the Spedora cycling training app, served by GitHub Pages on the custom
domain in `CNAME`:

- Privacy policy: `privacy/index.html` → https://spedora.app/privacy/
- Terms of use (with the health notice): `terms/index.html` → https://spedora.app/terms/
- Impressum: `imprint/index.html` → https://spedora.app/imprint/
- The same pages in German, French, Spanish and Italian under `de/`, `fr/`, `es/` and `it/`,
  e.g. https://spedora.app/de/privacy/ (each page links to its other languages)

The pages are generated in the app repo (ctfle/cycplan) from the same text the app shows
(`src/components/legal/PrivacyPolicy*.tsx`, `src/components/legal/TermsOfUse*.tsx`,
`src/components/ImprintContent.tsx`) by
`npx vite-node scripts/buildLegalPages.ts`, which writes them to `docs/`. Change the text there
and copy the generated files here, so the app and these pages always say the same thing.
Keep `CNAME` when copying; without it GitHub Pages drops the custom domain.

GitHub Pages: Settings → Pages → Deploy from a branch → `main`, `/ (root)`; custom domain
`spedora.app`, Enforce HTTPS on.

DNS for spedora.app (DNS only, not proxied):

| Type  | Name  | Value                                                      |
|-------|-------|------------------------------------------------------------|
| A     | `@`   | 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153 |
| AAAA  | `@`   | 2606:50c0:8000::153, 2606:50c0:8001::153, 2606:50c0:8002::153, 2606:50c0:8003::153 |
| CNAME | `www` | ctfle.github.io                                            |

The iCloud+ mail records (MX, TXT) on `@` stay as they are.
