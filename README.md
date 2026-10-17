# VRNas Landing

Landing page for **VRNas**, a fictional VR services company. It is built pixel-close to a Figma mockup with plain HTML and CSS.

**Live:** https://tretyakweb.github.io/vrnas-landing/

The page is built one section at a time, with the help of [Claude Code](https://claude.com/claude-code) and the Figma MCP server.

## Stack

- Plain **HTML + CSS**: no frameworks, no build step
- [Chakra Petch](https://fonts.google.com/specimen/Chakra+Petch) from Google Fonts
- BEM class naming, design tokens as CSS custom properties

## Run locally

```bash
git clone https://github.com/TRETYAKweb/vrnas-landing.git
cd vrnas-landing
python3 -m http.server 5173
```

Then open http://localhost:5173.

## Project structure

```
index.html          page markup, one <section> per block
css/style.css       tokens, styles per section, media queries at the end
assets/icons/       SVG icons
assets/images/      photos (PNG) and background decor (SVG)
documentation/      one document per technical decision
CLAUDE.md           project rules and progress for Claude Code
```

## Progress

| # | Section | Status |
|---|---|---|
| 1 | Header + Hero + Features | ✅ Done |
| 2 | About Us | ⏳ Next |
| 3 | Our Service | — |
| 4 | Why Choose Us | — |
| 5 | How to Get Started | — |
| 6 | Testimonial | — |
| 7 | Our Pricing | — |
| 8 | Our Trusted Partners | — |
| 9 | Our Articles | — |
| 10 | Subscribe | — |
| 11 | Footer | — |

## How it is built

Each section follows the same loop:

1. Pull the section's design context and assets from Figma through the Figma MCP server.
2. Lay it out with grid/flex. Absolute positioning from Figma is used only for decorative layers.
3. Check it in the browser at 1440px, 2000px and 375px against the mockup.
4. Record decisions and pitfalls in `documentation/` with the `/update-docs` skill.

Commits follow [Conventional Commits](https://www.conventionalcommits.org).

## Credits

The design is based on the **VRNas** Figma mockup. All design rights belong to its original authors. This repository is a learning project.
