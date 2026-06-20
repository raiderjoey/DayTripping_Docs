# DayTripping — Legal documents

- `privacy-policy.md` — Markdown source (edit this; keep it the source of truth).
- `privacy-policy.html` — Self-contained, ready-to-host page for GitHub Pages.

## Hosting on GitHub Pages

Don't enable Pages on the private app repo (it would expose the source). Use a
small **public** repo for legal pages instead:

1. Create a public repo, e.g. `daytripping-legal`.
2. Copy `privacy-policy.html` into it. Rename it to `index.html` if you want the
   policy at the repo root URL, or keep the name to serve it at `/privacy-policy.html`.
3. In the repo: **Settings → Pages → Build and deployment → Source:**
   *Deploy from a branch* → branch `main`, folder `/ (root)` → **Save**.
4. Wait ~1 minute. Your URL will be:
   - `https://<your-username>.github.io/daytripping-legal/` (if renamed to `index.html`), or
   - `https://<your-username>.github.io/daytripping-legal/privacy-policy.html`

## Where to put the URL in the stores

- **Google Play Console:** Policy → App content → Privacy policy → paste the URL.
  (Also complete the Data safety form to match this policy.)
- **Apple App Store Connect:** App Privacy → Privacy Policy URL, and your app's
  General Information → Privacy Policy URL. (Also complete the App Privacy
  "nutrition label" questionnaire to match this policy.)

## Keep it accurate

If the app's data practices change, update `privacy-policy.md`, re-export the
HTML, and bump the "Last updated" date.

Crash reporting (Firebase Crashlytics) shipped in v2.0.1 and is reflected in the
policy as of the June 19, 2026 revision. This adds a **Diagnostics → Crash data**
category that both store privacy forms must now declare (see below). Still on the
roadmap and NOT yet present: Firebase Analytics, Performance Monitoring, App
Check. Add them to the policy when/if they ship.

### Store privacy-form impact of Crashlytics

- **Apple App Privacy:** declare **Diagnostics → Crash Data**. Crashlytics links
  crashes to an opaque user ID, so this data is "Linked to the user," used for
  **App Functionality** only (not tracking).
- **Google Play Data safety:** declare collection of **Crash logs** (and
  **Device or other IDs** for the attribution identifier), purpose **App
  functionality / Analytics-style diagnostics**, encrypted in transit, not sold.
