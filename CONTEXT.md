# CONTEXT.md — Glossary of terms for the Comunidade Vitral site

## Glossary

- **content source**: The authoritative markdown files used for site content. Located in `docs/conteudo/novo/` for all pages except the Home page, which is sourced from `docs/conteudo/homepage.md`. (Decision: adopted per AGENTS.md; legacy root files moved to `docs_old/`.)
- **legacy archive**: Directory `docs_old/` containing markdown files and directories that are no longer used for the live site but retained for reference. Includes former `docs/conteudo/` root files (except homepage), `docs/propostas/`, `docs/openspec-legado/`, and `docs/raw/`.
- **design system**: The visual identity "Marca Nova" defined in `docs/specs/marca-nova.md` and implemented via CSS tokens in `css/tokens.css`.
- **deployment branch**: The Git branch `homologacao` whose root is served by GitHub Pages at `https://ismaelmmachado.github.io/comunidadevitral/`. The `main` branch is used only for explicit deploys.
- **salva**: Colloquial term meaning "commit and push to the `homologacao` branch".
- **salva em main**: Explicitly commit and push to the `main` branch for deploy.

## Notes

- The site is a static HTML/CSS/JS site with no build step.
- Header and footer are duplicated across all HTML pages; changes require updating each file.
- JavaScript is limited to `js/menu.js` for mobile menu toggle.