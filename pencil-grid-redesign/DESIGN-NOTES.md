# Pencil Grid — design notes for mivillavicencio.com

Handoff from a design prototyping session. `index.html` + `style.css` + `assets/portrait.jpg`
are a static, dependency-free version of the chosen direction ("G · Pencil Grid").
The site is hosted on GitHub Pages with a custom domain (Porkbun).

## The idea
Professional, academic, quiet — but with real design literacy rather than a template look.
Pastel, sleek, discreet. Nothing neon, no gradients-as-decoration, no "AI startup" tropes.

References the design is built on (keep these in mind when changing anything):
- **Agnes Martin** — late pastel bands (rose, butter, powder) and hand-ruled graphite grids.
  Source of the palette, the faint ruled lines on the page, and the hero "painting".
- **Karl Gerstner / Wim Crouwel / Swiss style** — asymmetric layout on a modular grid,
  a fixed label column + body column, generous whitespace, hairline rules.
- **The New Typography (Moholy-Nagy, Tschichold)** — asymmetric, ranged-left text, clarity first.
- **Kenya Hara** — emptiness as a deliberate element; don't fill space just because it's there.

## Type
- **Ysabeau** (Christian Thalmann, Google Fonts, OFL) — a sans serif built on Garamond's proportions.
  Display: weight 300, tight tracking. Statement: 300 italic.
- **Ysabeau Office** for body text (better for running text).
- **Ysabeau SC** (small caps) for labels, nav, and link rows, letterspaced 0.06–0.1em.
- Wanted later: try **"Sometimes"** by Balázs Szemmelroth (free; Times New Roman with selected
  serifs removed) as the display face — I liked that "sans Times" look. Self-host the woff2 if used.

## Tokens (all in `:root` in style.css)
- Paper `#F5F4EF`, raised paper `#FBFAF6`, ink `#22211F`, muted `#5E5C57` (AA on paper), rules `#D8D5CC`.
- Pastels `--p1/--p2/--p3`: rose `#EFD3CC`, butter `#F0E5BF`, powder `#CFDDE8`.
  Alternates: "Powder, sage, lilac" `#CFDDE8 #D5E0CF #DDD6EA`; "Dusk" `#E9CFD6 #DDD6EA #F1DFC6`.
- Pastels are for fields/marks only — never for text (they fail contrast).

## Structure
- Header: small-caps wordmark left, small-caps nav right, hairline rule below.
- Hero: big light name + italic one-sentence research statement; to the right, the
  "Study for an interval" square — pastel bands with feathered edges (certainty fading out)
  under a graphite grid. It's a quiet visual pun on uncertainty intervals; keep it subtle.
- Catalogue rows with roman numerals: i. about, ii. news, iii. publications. Label column 220px.
- Publications get a tiny band "thumbnail" (swap for real paper figures later, or keep).
- Colophon footer crediting the typeface and references (a designer's touch — keep it).

## Open TODOs
- [ ] Real links: email, CV PDF, Google Scholar, GitHub, LinkedIn, Fumeng Yang, FIGX Lab, Qianwen Wang, paper/arXiv/BibTeX.
- [ ] Fill in co-authors on the FAccT 2026 paper (currently `[CO-AUTHORS]`).
- [ ] Replace `assets/portrait.jpg` with the original high-res photo (current one is cropped from a screenshot).
- [ ] Decide how this fits the existing repo (plain HTML vs. Jekyll/theme) — see prompt below.
- [ ] Favicon, Open Graph image/meta, and a print stylesheet.
- [ ] Check at phone width (layout already wraps; label column stacks above body).
- [ ] Possibly: teaching section (TA, CMSC 422 Machine Learning, 2026–27), separate CV page.

## Starter prompt for Claude Code
> I'm redesigning my academic website (this repo, deployed on GitHub Pages at mivillavicencio.com).
> The new design is in `redesign/` (index.html, style.css, assets/, DESIGN-NOTES.md) — read DESIGN-NOTES.md first.
> 1. Look at how the current site is built (plain HTML? Jekyll? a theme like al-folio?) and tell me
>    how you'd adopt this design with the least friction — replacing the theme's layout/CSS or
>    switching to the plain static version. Don't change anything yet.
> 2. Then port the design, pulling real content (bio, news, publications, links) from the existing site
>    instead of the placeholders, and keep the existing domain/CNAME setup working.
> 3. Keep the design principles in DESIGN-NOTES.md: pastel, quiet, asymmetric grid, Ysabeau type,
>    no new colors or effects unless I ask. Show me a local preview before committing.
