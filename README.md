# Eigenvectors from First Principles

An interactive, single-chain explanation of eigenvectors — from the definition of a coordinate all the way through the characteristic equation and into PCA — built as a pair of static HTML pages for GitHub Pages.

No frameworks. No build step. Just open the files.

## Why this exists

Eigenvectors are typically taught as a computational procedure buried under layers of prerequisite jargon. You're told to "find the eigenvalues of this matrix" long before anyone explains *why* a matrix has special directions at all, or what it even means for a transformation to "collapse."

This project rebuilds the idea from scratch: coordinates → vectors → matrices as verbs → the determinant (derived from axioms, not memorised) → the characteristic equation → eigenvectors → power iteration → PCA on real data. Every step earns the next. Every claim has an interactive figure you can drag.

It started as handwritten notes on an iPad ([`notes.pdf`](notes.pdf)) — a Freeform board where I sketched the dependency chain while trying to build my own intuition. The two HTML pages are those notes turned into something you can interact with and share.

## The pages

| File | What it is |
|---|---|
| [`index.html`](index.html) | The article — nine sections of prose, six interactive figures (transformation explorer, area morph, box-subtraction proof, characteristic polynomial finder, power iteration, fish size-axis explorer) |
| [`concept-map.html`](concept-map.html) | The atlas — a dependency constellation of 20 concepts and 38 edges, a 13-rung math ladder, and a sourced literature section drawing from 3Blue1Brown, Medium, and elsewhere |
| [`notes.pdf`](notes.pdf) | The original Freeform notes that started it all |

## Deploy

Drop the files in a GitHub repo, enable Pages (Settings → Pages → Deploy from branch → `main` / `/ (root)`), and the site is live. Both pages cross-link each other with relative paths — keep them in the same folder.

## Interactive figures

All visualisations are inline SVG drawn with vanilla JavaScript. They respond to pointer drag, sliders, and buttons. Everything runs client-side with zero dependencies beyond KaTeX (loaded from CDN for math typesetting).

**Article highlights:**
- **Transformation explorer** — drag a vector through any 2×2 matrix; eigen-detection fires when input and output align
- **Determinant area morph** — watch the unit square inflate into a parallelogram; area readout tracks det(A) exactly
- **Fish size-axis** — rotate a line to maximise captured spread by hand, then reveal that the eigenvector finds the same answer

**Concept map highlights:**
- **Dependency constellation** — hover any concept to light its full prerequisite lineage (amber) and what it unlocks (teal); click to open intuition + math + mini-vignette + literature reference
- **Trace path** — animate the topological order from foundations to Eigenvector or PCA
- **Math ladder** — 13 rungs building notation from *a ∈ ℝ* to *Av = λv* to PCA

## Tech

- Single-file HTML, all CSS in `<style>`, all JS in `<script>`, all figures as inline SVG
- One external dependency: [KaTeX](https://katex.org) via jsDelivr CDN
- Light + dark mode via `prefers-color-scheme`
- Responsive down to 360px
- Accessible: `role="img"`, `<title>`/`<desc>` on every SVG, screen-reader summaries on interactive widgets

## License

The code and prose are yours to learn from. Attribution appreciated if you share or remix.
