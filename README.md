# PolyStack — Computer Engineering Diploma, Learning Site

A learning-focused site for a polytechnic Computer Engineering diploma program — curriculum, reference library, and hands-on practice tools, aimed at 15–19 year-olds working through the subject.

**Live demo:** enable GitHub Pages on this repo (Settings → Pages → Source → GitHub Actions) and it'll deploy automatically — a workflow is already included.

## What's here

- `index.html` — the main page: hero with a real interactive WebGL chip (drag/swipe to rotate, three.js), curriculum cards for all six semesters (each with an expandable "what you'll actually do" explainer), a lateral-entry pathway diagram, a feature grid, and an FAQ.
- `library.html` — a glossary (35 terms, each with a short and a longer expandable definition), a semester-by-semester reading list with search links to find each book, a live binary/decimal/hex/octal converter, and its own small interactive 3D "chip rack" visual.
- `practice.html` — three hands-on tools: a logic gate simulator (AND/OR/NOT/XOR/NAND/NOR, live-updating from two toggles), flashcards covering all 35 glossary terms, and a data structures playground (stack push/pop, queue enqueue/dequeue, and a step-through bubble sort visualizer).
- `favicon.svg` / `favicon-32.png` / `apple-touch-icon.png` — the site's icon (a DIP-chip mark) at the sizes browsers ask for.
- `og-image.png` — the 1200×630 image shown when the link is shared on social/chat apps.
- `sitemap.xml` / `robots.txt` — basic crawlability, pointed at the deployed GitHub Pages URL.

## Stack

Plain HTML/CSS/JS, no build step, no framework, no backend. three.js (used on `index.html` and `library.html` only) loads via an ES module import map pointing at the latest published release — nothing to install, nothing to run.

```html
<script type="importmap">
{ "imports": { "three": "https://cdn.jsdelivr.net/npm/three@latest/build/three.module.js" } }
</script>
```

`practice.html` is plain JS with no three.js dependency — it's UI-interaction focused, not 3D.

## Design system

Grounded in the physical material of computer engineering rather than a generic SaaS look — copper traces on dark solder-mask green, DIP-chip silhouettes, a PCB grid texture. Colors and type live as CSS custom properties at the top of each file's `<style>` block if you want to retheme it.

## A note on the book links

Each book card links to an Amazon India *search* for that title, not a specific product page — real published textbooks are copyrighted, so there's no free "download," and I didn't want to guess at a specific listing that might be wrong or dead.

## A note on the URLs

Canonical URLs, sitemap, and Open Graph tags are pointed at `https://pain8055.github.io/Computer-Engineering/`. If this repo's name or owner changes, update those in the `<head>` of all three HTML files and in `sitemap.xml`/`robots.txt`.

## Known limitations (by design)

- No backend — this is a static front-end concept. There's no email signup or form pretending to send anywhere.
- Not an accredited institution — all program details are illustrative.
- The flashcard/glossary data is duplicated between `library.html` and `practice.html` since there's no build step or shared module system — if you edit a term's definition, update both files.

## Local development

No build step. Open `index.html` directly, or serve the folder locally:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## License

MIT — see `LICENSE`.
