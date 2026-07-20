# WUNDERKAMMER

**A cabinet of computational curiosities — eight living algorithms, drawn in real time, no images anywhere on the page.**

*Wunderkammer* (n.) — a "cabinet of wonders," the Renaissance predecessor to the museum: a single room where naturalia and artificialia were displayed side by side, each specimen given its own label and small mystery.

Every exhibit here is a law of nature kept alive in your browser — a few dozen lines of arithmetic, computing every frame as you watch. Nothing is a photograph. Press **Reseed** on any plate and the specimen is born again, never quite the same twice.

**Live:** https://wunderkammer-alpha.vercel.app

## The collection

| | Specimen | Algorithm |
|---|---|---|
| WK.001 | *Flumen ignotum* — the unknown river | ~3,000-particle noise-field advection |
| WK.002 | *Sturnus calculans* — the counting starling | Boids murmuration (Reynolds' three rules) |
| WK.003 | *Corallium chemicum* — chemical coral | Gray–Scott reaction–diffusion |
| WK.004 | *Limes crescens* — the growing border | Differential growth (a ring that folds as it stretches) |
| WK.005 | *Papilio deterministicus* — the deterministic butterfly | Lorenz attractor, three trajectories |
| WK.006 | *Mycelium electricum* — electric mycelium | Space colonization toward scattered attractors |
| WK.007 | *Unda stans* — the standing wave | Per-pixel interference of moving wave sources |
| WK.008 | *Helianthus aureus* — the golden sunflower | Phyllotaxis (one seed every 137.5°) |

Each plate carries a museum wall label — accession number, Latin name, medium, and a curator's note — in the style of a natural history collection, not a tech demo.

## Running it

It's a single self-contained HTML file — no frameworks, no build step, no dependencies.

**Easiest:** double-click `index.html`.

**Or serve it:**

```sh
python -m http.server 4188
# then open http://localhost:4188
```

## Notes

- Plates pause automatically when scrolled off-screen (`IntersectionObserver`) and resume on return, so the gallery stays cheap regardless of length.
- Respects `prefers-reduced-motion` — each simulation fast-forwards to a settled still instead of animating.
- Responsive down to mobile; visible keyboard focus on every control.
- Dev hook: `window.__wk` is an array of the page's `Plate` instances (hero + all eight specimens) — `.setup()`, `.sim.frame(t)`, and `.reseed()` let you drive or inspect any simulation headlessly.

---

Built by [Claude](https://claude.com/claude-code). Every specimen is real arithmetic, not a picture of one.
