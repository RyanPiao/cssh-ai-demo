# CSSH AI in Teaching — Resource Hub

Live site: **https://ryanpiao.github.io/cssh-ai-demo/**

A faculty-facing resource hub for the CSSH AI Curricular Transformation Initiative.

## Pages
| File | What it is |
|---|---|
| `index.html` | Start here — "what do you need?" paths, key rules, featured examples |
| `policies.html` | University AI rules in plain language + copyable syllabus statements, assignment labels, disclosure template |
| `assignment-toolkit.html` | Self-serve toolkit — AI-resilient fixes by type, Build AI in, Check authentic work. Tabs are linkable (`#disc`, `#paper`, `#quant`, `#any`, `#integrate`, `#verify`) |
| `examples.html` | Filterable gallery of all interactive examples |
| `get-help.html` | Contacts, consult request, cohort/workshops, university support, guides |
| `faq.html` | Common faculty questions (accordion) |
| `about.html` | About the site + sources & credits |
| `resources/resource-card.pdf` | Printable 2-up resource card with QR (source: `resources/resource-card.html`; regenerate with headless Chrome `--print-to-pdf`) |
| `demo-live.html` | Live-session page — auto-generates scan-to-join QR codes |
| `styles.css` | Shared Northeastern-style design system (edit once, all pages update) |
| `examples.json` | **The one file you edit to add examples** |

## ➕ How to add a new example (the easy way)

Everything on the Examples gallery, the hub's "in action" row, and the live-demo QR page is generated from **one file: `examples.json`.** To add an example, append an object:

```json
{
  "title": "Short name",
  "blurb": "One sentence on what it is / why it's AI-aware.",
  "url": "https://... (or a relative path like artifacts/my-demo.html)",
  "discipline": "Economics",
  "type": "Interactive tool",
  "format": "Web page",
  "featured": true
}
```

`type` = Interactive tool | Live activity | Assessment redesign | Concept.
`format` (optional) = what the link opens, e.g. Slide deck | Web page | PDF.
`featured: true` also shows it on the Start here page.

That's it. The gallery re-renders, the filter buttons rebuild themselves from the data, and if `type` is **Interactive tool** or **Live activity** it also appears as a scan-to-join QR on `demo-live.html`. No HTML editing.

- **New self-contained demo page?** Drop the HTML in `artifacts/` and point `url` at it.
- **New discipline or type?** Just use it in an entry — the filters build from the data.

## Notes
- Interactive pages (charts/polls/games) live in the separate public `econ-lectures` repo; examples just link to them.
- Design changes go in `styles.css` only.
- QR for the hub itself is `qr/hub.svg`.
