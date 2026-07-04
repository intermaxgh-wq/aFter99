# AFTER9 — Static Site

Static export of the AFTER9 site, ready for GitHub Pages.

## Structure
```
index.html
style.css
script.js
assets/img/tee-front.jpg
assets/img/tee-back.jpg
assets/img/about-graphic.jpg
```

## Deploy to GitHub Pages
1. Push this folder's contents to the root of a GitHub repo.
2. In the repo: **Settings → Pages → Build and deployment → Source** → "Deploy from a branch".
3. Pick the `main` branch and `/ (root)` folder, then Save.
4. Live at `https://<username>.github.io/<repo-name>/` within a minute or two.

## Before you go live
Carried over from your source file — none of these are things the export changed, just placeholders/notes already in your code worth double-checking:

1. **Paystack public key** — `script.js` line 4 still has a placeholder (`pk_test_xxxx...`). Swap in your real public key from the Paystack dashboard or checkout will fail.
2. **Formspree form ID** — the "Notify Me" form still posts to `https://formspree.io/f/YOUR_FORM_ID`. Replace with your real endpoint.
3. **Admin password is in plain text** — `ADMIN_PASSWORD = 'NBA123DR'` sits directly in `script.js`. Your own code comment already flags this as a convenience UI, not real security — worth remembering that on a public GitHub Pages site, anyone can view-source (or read the repo) and see it.
4. **What ships live by default** — right now `LE_STATE` and `DROP_CONFIG` in `script.js` default to: tee photos **blurred**, stock **99/99**, drop **not** forced live, countdown targeting `2026-08-01T12:00:00+00:00`. That's what every visitor sees on load. The on-page Admin panel only changes things in your own browser tab for previewing — it resets on refresh and doesn't touch what other visitors see. To change the real default, edit those values in `script.js` directly and redeploy.
5. **Contact form is front-end only** — the bottom "Send message" form just flips its button text to "Sent ✓"; it isn't wired to anything. Point it at Formspree (or similar) if you want those messages to actually arrive somewhere.
