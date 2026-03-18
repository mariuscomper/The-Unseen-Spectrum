# The Unseen Spectrum

**An interactive data exploration of color vision deficiency — prevalence, impact, and lived experiences worldwide.**

🔗 **[View the live page →](https://yourusername.github.io/the-unseen-spectrum/)**

![Preview](https://img.shields.io/badge/responsive-desktop%20%26%20mobile-1d3557) ![License](https://img.shields.io/badge/license-MIT-27ae60) ![Dependencies](https://img.shields.io/badge/dependencies-none-e74c3c)

---

## About

Color vision deficiency (CVD) affects approximately 350 million people worldwide — up to 8% of males and 0.5% of females — yet most individuals remain undiagnosed until adolescence or adulthood. This interactive webpage synthesises epidemiological data, classification, psychosocial impact, and policy recommendations from the peer-reviewed literature into an accessible, visually rich experience.

Based on the review paper:

> **"A Global Perspective of Color Vision Deficiency: Awareness, Diagnosis, and Lived Experiences"**
> Ali Almustanyir — *Healthcare* (2025), 13(16), 2031.
> DOI: [10.3390/healthcare13162031](https://doi.org/10.3390/healthcare13162031)

## Features

- **Global prevalence data** — Animated horizontal bar charts comparing male and female CVD rates across 14+ populations
- **CVD type breakdown** — Card-based classification of protan, deutan, tritan, and achromatic deficiencies with prevalence figures
- **Real-time colour simulation** — Canvas-based CVD simulator using colour-science transformation matrices (Brettel, Viénot) applied to a rich test scene with traffic lights, rainbow, flowers, and colour swatches
- **Impact severity meters** — Animated progress bars showing relative impact across educational, occupational, and psychosocial domains
- **Awareness gap statistics** — Key figures from Nigeria, Australia, and occupational studies
- **Diagnosis timeline** — Visual pathway from early signs to late discovery
- **Evidence-based recommendations** — Actionable guidance for educators, clinicians, and employers

## Technical details

| Feature | Implementation |
|---------|---------------|
| Framework | Vanilla HTML/CSS/JS — zero dependencies |
| Typography | DM Serif Display + IBM Plex Sans + IBM Plex Mono (Google Fonts) |
| Animations | CSS `@keyframes` + `IntersectionObserver` scroll-triggered reveals |
| CVD simulation | Canvas 2D pixel manipulation with sRGB ↔ linear RGB gamma correction |
| Dark mode | Full support via `prefers-color-scheme` CSS media query |
| Responsive | Mobile-first with `clamp()` fluid typography, CSS Grid auto-fit |
| Performance | No build step, no bundler, single HTML file under 30 KB |

## Deployment

### GitHub Pages

1. Fork or clone this repository
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch** → `main` / `root`
4. Your site will be live at `https://yourusername.github.io/the-unseen-spectrum/`

### Any static host

Just serve `index.html`. That's it — there are no dependencies to install, no build step, no configuration.

```bash
# Local preview
python3 -m http.server 8000
# then open http://localhost:8000
```

## Project structure

```
the-unseen-spectrum/
├── index.html      # Complete self-contained webpage
└── README.md       # This file
```

## Colour simulation methodology

The CVD simulator applies linear algebra transformations to pixel data in the sRGB colour space. The pipeline:

1. **sRGB → Linear RGB** — Inverse gamma correction (IEC 61966-2-1)
2. **Matrix multiplication** — Simulation matrices derived from Brettel, Viénot, and Mollon (1997) for dichromatic observers
3. **Linear RGB → sRGB** — Forward gamma correction
4. **Clamping** — Values bounded to [0, 1] before 8-bit quantisation

These are approximations and may not perfectly represent individual CVD experiences, which vary in severity.

## Data sources

All data points are drawn from the review paper cited above, which synthesises findings from:

- Birch (2012) — worldwide prevalence of red-green CVD
- Chakrabarti (2018) — psychosocial aspects and lived experience quotes
- Hathibelagal (2022) — occupational implications
- Woldeamanuel & Geta (2018) — Ethiopian school screening
- Harrington et al. (2021) — Republic of Ireland prevalence
- Mashige (2019) — South Africa / Durban study
- Multiple additional epidemiological studies across 15+ countries

## License

MIT — free to use, modify, and distribute.

## Contributing

Issues and pull requests welcome. If you have additional CVD prevalence data, improved simulation matrices, or accessibility improvements, please contribute.

---

<sub>Built with care for those who see the world differently.</sub>
