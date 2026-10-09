# Diplomatic Pouch — Site Package

The complete self-contained static site for the Diplomatic Pouch publication.
Ready to deploy to Cloudflare Pages, Netlify, GitHub Pages, or any static host.

## Pages

- `index.html` — **Public homepage.** Magazine-style front page with hero masthead,
  featured latest dispatch, and grid of recent dispatches. This is what readers see.
- `archive.html` — **Editorial dashboard.** Full filterable grid of all dispatches with
  status pips, search, and admin notes. Linked from the homepage's "Archive" nav item.
- `manifesto.html` — The publication's opening manifesto
- `issue-002.html` through `issue-016.html` — The fifteen numbered dispatches
- `cover-*.png` — Cover images (one per dispatch)

## Reader experience

1. Visitor lands on `index.html` — sees the publication identity, latest dispatch
   prominently featured, grid of recent work below
2. Clicks any tile → opens that dispatch's HTML page
3. Reads the dispatch (hero cover at top, dispatch body below)
4. Returns to homepage or clicks another tile

No login, no download, no account required.

## Deploying to Cloudflare Pages

1. Create a free account at [cloudflare.com](https://dash.cloudflare.com/sign-up)
2. Click **Workers & Pages** → **Create** → **Pages** → **Upload assets**
3. Project name: `diplomatic-pouch` (or whatever you prefer)
4. Drag this entire folder onto the drop zone
5. Click **Deploy site**

Your publication is live at `diplomatic-pouch.pages.dev` within 60 seconds.

## Adding a new dispatch

1. Build the new dispatch HTML (e.g., `issue-018.html`) and its cover (`cover-018.png`)
2. Drop both files into this folder
3. Open `index.html` in a text editor
4. Find the `DISPATCHES` array near the top of the `<script>` block
5. Add a new object to the array with the dispatch metadata, and set `featured: true`
   on the new one (remove `featured: true` from the previous latest dispatch)
6. Open `archive.html` and add the same dispatch to its own `DISPATCHES` array
7. Re-deploy

## Technical notes

**Pure HTML/CSS/JS.** No frameworks. No build step. Works on any browser, any device.

**Mobile-first design.** Hero masthead scales fluidly; the featured dispatch stacks
cover-above-text on mobile; dispatch pages open directly to the title and cover.

**Dark mode.** Automatic based on system preference. Manual toggle in bottom-right of
every page. Preference persists in browser localStorage.

**Issue 017.** Currently hidden from the public homepage because the dispatch text is
not yet written. The cover exists. When the dispatch is ready, add it back to the
`DISPATCHES` array in both `index.html` and `archive.html`.

---

*Diplomatic Pouch — a weekly dispatch on the security, equity, and architecture
of the systems we live inside. By Dr. Safi Mojidi.*
