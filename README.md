# ai.bystruev.com

Trilingual landing page selling predictable **n8n + LLM automation**
(“engineer & rails” method) with worked examples from three industries.

- `/` — English (default), `es/` — Español, `ru/` — Русский.
- Every page carries a language switch in the header.
- Pure static HTML + one `style.css`. No build step, no JavaScript.

## Preview (how the site looks)

English:

![English landing page](preview/preview-en.png)

Español:

![Página en español](preview/preview-es.png)

Русский:

![Страница на русском](preview/preview-ru.png)

## Local preview

```bash
cd ~/ai.bystruev.com && python3 -m http.server 8080
# open http://localhost:8080
```

(`~/ai.bystruev.com` is a symlink to `~/Downloads/GitHub/dbystruev/ai.bystruev.com`.)

## Deploy

Any push to `main` is published by GitHub Pages within ~1 minute:

```bash
git push origin main
```

## URLs

Custom domain (via `CNAME` file in this repo):

- EN: `https://ai.bystruev.com/`
- ES: `https://ai.bystruev.com/es/`
- RU: `https://ai.bystruev.com/ru/`

DNS: `ai.bystruev.com` → CNAME `dbystruev.github.io`.
HTTPS is provisioned by GitHub automatically — tick **Enforce HTTPS**
under **Settings → Pages** once the certificate is ready.

## To customize

- Contact email is `ai@bystruev.com` in all three `index.html`
  files (add your Telegram next to it — marked in the contact section).
