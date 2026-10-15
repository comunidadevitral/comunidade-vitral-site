Status: ready-for-agent

## Problem Statement

The project documentation was scattered across multiple folders (openspec/, docs/superpowers/, docs/inventario.md, duplicate content in docs/conteudo/ and docs/conteudo/novo/, etc.), making it hard to find the source of truth and leading to outdated or duplicated information. This caused confusion for contributors and increased maintenance overhead.

## Solution

Consolidated documentation by moving spec-driven content to docs/specs/, historical material to docs_old/, updated references in AGENTS.md, CONTEXT.md, README.md, and established a clear content source in docs/conteudo/novo/ (with homepage.md). Removed the openspec/ folder entirely. The legacy archive (docs_old/) retains historical material for reference.

## User Stories

1. As a developer, I want to find the current design system specification in one place, so that I can reference it without searching multiple locations.
2. As a contributor, I want to know where the source of truth for site content is, so that I can update the correct files.
3. As a maintainer, I want obsolete documentation to be archived, so that the active documentation folder only contains relevant files.
4. As a contributor, I want the project configuration to reference the correct paths, so that I don't get broken links.
5. As a reviewer, I want the AGENTS.md and CONTEXT.md to accurately reflect the current project structure, so that I can trust the documentation.

## Scenarios

1. Given the project root, When I look for the design system spec, Then I find it at docs/specs/marca-nova.md.
2. Given the project root, When I look for the site estatico vitral spec, Then I find it at docs/specs/site-estatico-vitral.md.
3. Given the project root, When I look for the spec-driven config, Then I find it at docs/specs/config.yaml.
4. Given the project root, When I look for historical changes, Then I find them in docs/changes/archive/.
5. Given the project root, When I look for the content source for a page (except home), Then I find it in docs/conteudo/novo/<page>.md.
6. Given the project root, When I look for the content source for the home page, Then I find it at docs/conteudo/homepage.md.
7. Given the project root, When I look for the openspec folder, Then I find that it has been removed.
8. Given the project root, When I check AGENTS.md for documentation references, Then I see references to docs/specs/ and not openspec/.
9. Given the project root, When I check CONTEXT.md for design system definition, Then I see it points to docs/specs/marca-nova.md.
10. Given the project root, When I check README.md for spec locations, Then I see references to docs/specs/.

## Implementation Decisions

- Documentation folders: Moved openspec/specs/* to docs/specs/*. Moved openspec/changes/archive to docs/changes/archive. Removed the empty openspec/ directory.
- Configuration references: Updated AGENTS.md lines 20, 29, 57 to point to docs/specs/marca-nova.md and docs/specs/. Updated CONTEXT.md line 7 to point to docs/specs/marca-nova.md. Updated README.md lines 40-42 to point to docs/specs/marca-nova.md, docs/specs/site-estatico-vitral.md, and docs/changes/archive/.
- Content source: Reinforced that docs/conteudo/novo/* (except homepage.md) and docs/conteudo/homepage.md are the source of truth, per AGENTS.md. Removed duplicate homepage.md in docs/conteudo/novo/ and moved legacy root conteudo files to docs_old/.
- Legacy archive: Moved docs/superpowers/ and docs/inventario.md to docs_old/ for reference.

## Testing Decisions

- Verified that no HTML, CSS, JS, or markdown files (outside of docs_old/) contain references to the old openspec/ paths.
- Confirmed that the site still serves correctly by checking that the local server on port 4321 returns the expected HTML.
- Ensured that all links in AGENTS.md, CONTEXT.md, and README.md are valid and point to existing files.
- Validated that the content source files exist and are not duplicated unnecessarily.

## Out of Scope

- Changes to the actual site content (text, images, design tokens).
- Modifications to the site's HTML, CSS, or JavaScript.
- Alterations to the deployment process or GitHub Pages configuration.
- Changes to the issue tracker configuration or agent skills.

## Further Notes

This spec captures the normalization work performed to streamline documentation and reflect the current state of the project. Future documentation efforts should adhere to the established structure: specs in docs/specs/, historical material in docs_old/, and content source in docs/conteudo/novo/ (with homepage.md).