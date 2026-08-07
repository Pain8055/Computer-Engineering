# PolyStack — Computer Engineering Diploma Landing Page

A concept landing page for a polytechnic Computer Engineering diploma program, aimed at 15–19 year-olds and their parents comparing a diploma path against a straight B.Tech.

**Live demo:** enable GitHub Pages on this repo (Settings → Pages → Deploy from branch → `main` → `/root`) and it'll be served automatically — a workflow is already included.

## What's here

- `index.html` — the main landing page: hero with a real interactive WebGL chip (drag/swipe to rotate, built with three.js), curriculum cards, a lateral-entry pathway diagram, feature grid, FAQ, and a CTA.
- `library.html` — a second page: a computer engineering glossary (35 terms, each with a short and a longer expandable definition) and a semester-by-semester reading list, with live search and filtering.

## Stack

Plain HTML/CSS/JS, no build step, no framework, no backend. three.js is loaded via an ES module import map pointing at the latest published release — nothing to install, nothing to run.

```html
<script type="importmap">
{ "imports": { "three": "https://cdn.jsdelivr.net/npm/three@latest/build/three.module.js" } }
</script>
```

## Design system

Grounded in the physical material of computer engineering rather than a generic SaaS look — copper traces on dark solder-mask green, DIP-chip silhouettes, a PCB grid texture. Colors and type live as CSS custom properties at the top of each file's `<style>` block if you want to retheme it.

## Known limitations (by design)

- No backend — this is a static front-end concept. There's intentionally no email signup or form that pretends to send anywhere; the CTAs just link to the curriculum and library sections.
- Not an accredited institution — all program details are illustrative.

## Local development

No build step. Just open `index.html` in a browser, or serve the folder locally:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## License

MIT — see `LICENSE`.
