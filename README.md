# smite2-captain-page

The public, standalone captain page for the [SMITE 2 Draft Tool](https://github.com/celestewish/smite-2-draft-tool). Hosted here (rather than Supabase Storage or an Edge Function) because Supabase forces `Content-Type: text/plain` on any HTML it serves unless you're on a paid custom-domain add-on — GitHub Pages doesn't have that restriction.

This repo holds a single self-contained static file, `captain.html`. It has no build step and no secrets: the embedded Supabase anon key is the same public, RLS-scoped key the desktop app ships with, safe to expose client-side like any Supabase web app. All live draft data is fetched at runtime from Supabase, keyed by the `?code=` share code in the URL.

Deployed via GitHub Pages from this repo's `main` branch. Not meant to be browsed directly — moderators generate the link (with a real share code) from inside the desktop app.
