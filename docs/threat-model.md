# ZeroJS Blog: Threat Model

Scope: `main` branch. Status: ✅ implemented · ⚠️ partial · 🔲 planned.

## 1. System overview

A static Astro site (Markdown/MDX content collections, RSS, sitemap) built at deploy time. There is no database, no authentication, no user input, no API routes, and the pages ship no client-side JavaScript of their own. The attack surface is the **build pipeline, dependencies, and content**.

## 2. Assets

Site integrity (what visitors see), the deploy pipeline credentials, and the author's reputation (defacement or malicious content injection).

## 3. Controls and status

| Threat | Control | Status | Evidence |
|---|---|---|---|
| Runtime injection / XSS from user input | No user input and no server runtime | ✅ | `src/pages/*` |
| Malicious content via MDX | MDX executes JavaScript at build time. Only the repo owner's content is accepted; third-party PRs touching `src/content` should be reviewed as code | ⚠️ | `@astrojs/mdx`, `src/content/` |
| Vulnerable or malicious dependencies | Lockfile committed (`package-lock.json`); a small dependency set (`astro`, `@astrojs/mdx`, `@astrojs/rss`, `@astrojs/sitemap`, `sharp`) | ⚠️ | `package.json` |
| Automated dependency/code scanning | Not configured | 🔲 | n/a |
| Security headers (CSP, HSTS, etc.) | Not set by this repo; depends on the hosting platform's configuration | 🔲 | n/a |
| Placeholder config | `site` is still `https://example.com`, which affects canonical URLs, RSS, and sitemap correctness | ⚠️ | `astro.config.mjs` |

## 4. Roadmap

1. Enable Dependabot and CodeQL; run `npm audit` in CI.
2. Add a `_headers` (or host-equivalent) file with CSP, HSTS, `X-Content-Type-Options`, and `Referrer-Policy`; the site needs no inline script, so a strict CSP is achievable.
3. Set the real `site` URL.
4. Require review on PRs that touch `src/content/**/*.mdx`.
