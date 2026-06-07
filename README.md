# UK Instant-Quote Demos

Free, self-contained demo pages for UK trade businesses, each showing an
**instant-quote chat widget** in action. One HTML file per prospect, served by a
single Vercel project at its own path:

```
your-project.vercel.app/template      ← Apex Roofing (master template)
your-project.vercel.app/<clientname>  ← one file per new client
```

Every demo is **100% client-side** — a scripted conversation, a hardcoded
itemised £ quote, and a mock "this is how the owner receives the lead" modal.
No backend, no API keys, no cost. It's a sales tool to show a prospect what
their website could have.

> This is the demo gallery. The real working product (AI backend + live pricing
> engine + email) is a separate project.

---

## Add a new client demo

1. **Copy** the template:
   ```powershell
   Copy-Item template.html clientname.html
   ```
2. **Edit** `clientname.html` — everything client-specific lives in three objects
   near the top of the `<script>`:
   - `CONFIG` — company name, sub-line, tagline, FB handle (for the logo),
     tooltip, quick-reply chips, currency.
   - `MSGS` — the scripted chat conversation.
   - `EST` — the itemised quote, the lead's details, extras, lead score, and the
     location/distance shown in the owner modal.
3. **(Optional) re-skin the colours** with a find/replace across the file:
   | Find | Role |
   |------|------|
   | `#163a74` | brand blue — dark |
   | `#1e4d96` | brand blue — mid |
   | `#2563eb` | brand blue — bright |
   | `#f59e0b` | accent — mid |
   | `#d97706` | accent — dark |
4. **Add a row** to `index.html` so it shows in the gallery.
5. **Commit & push** — Vercel auto-deploys it at `/clientname`.

---

## Local preview

Just open the `.html` file in a browser, or run any static server:

```powershell
npx serve .
```

## Deploy

Connected to a Vercel project — every push to `main` deploys automatically.
`vercel.json` enables clean URLs (`/template`, not `/template.html`).
