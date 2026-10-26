# AI on Rails

Trilingual landing page selling predictable **n8n + LLM automation**
(“engineer & rails” method) with worked examples from three industries.

- `/` — English (default), `es/` — Español, `ru/` — Русский.
- Every page carries a language switch in the header.
- Pure static HTML + one `style.css`. No build step, no JavaScript.

## Local preview

```bash
cd ~/ai-on-rails && python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy

Any push to `main` is published by GitHub Pages within ~1 minute:

```bash
git push origin main
```

## Custom domain (e.g. `www.example.com` → this page)

GitHub Pages serves custom domains with free HTTPS. Two places to touch —
**your DNS** and **this repo**. Pick one of the two setups:

### Option A — subdomain (`www.example.com`, recommended)

1. At your DNS provider, add a **CNAME** record:
   - Host: `www`, Value: `dbystruev.github.io`, TTL: auto/3600.
2. In this repo: **Settings → Pages → Custom domain** → type
   `www.example.com` → **Save**. (Or commit a file named `CNAME`
   containing exactly `www.example.com` — GitHub reads it automatically.)
3. Tick **Enforce HTTPS** once the certificate is issued (usually minutes).

### Option B — apex domain (`example.com`, no `www`)

GitHub Pages IPs change; always re-check the current list at
`https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site`.
As of 2026 the four **A** records are:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

1. At your DNS provider, add those four **A** records for `@`
   (and optionally a CNAME `www` → `dbystruev.github.io` that redirects).
2. Same repo step as Option A: **Settings → Pages → Custom domain** →
   `example.com` → Save → Enforce HTTPS.

### Verify

```bash
dig +short www.example.com      # expect dbystruev.github.io …
curl -sI https://www.example.com | head -3   # expect HTTP/2 200
```

DNS can take 5 min – 24 h to propagate. Until then the site keeps working at
`https://dbystruev.github.io/ai-on-rails/` (plus `/es/`, `/ru/`).

## To customize

- Contact email: search `hello@example.com` in the three `index.html`
  files and replace (add your Telegram next to it — marked in the contact
  section).
