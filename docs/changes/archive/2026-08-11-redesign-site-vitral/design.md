# Design — Site estático Comunidade Vitral (7 páginas)

## Context

Estado atual: repo `ismaelmmachado/comunidadevitral` com site Wix legado e protótipo de página única. O conteúdo institucional foi extraído e reorganizado em `docs/conteudo/novo/` (fonte da verdade). Motivação e escopo em `proposal.md`.

## Goals / Non-Goals

**Goals**
- Site estático multi-página, HTML5 + CSS puro, sem build step.
- Arquitetura de 7 páginas + 404, com header/footer compartilhados e tokens de design centralizados.
- Conteúdo verbatim; caminhos relativos para o subpath do Pages.
- Acessibilidade WCAG 2.1 AA e SEO por página.

**Non-Goals**
- Backend, CMS, build pipeline, PWA.
- Formulários de contato (contato via links diretos e WhatsApp).
- Framework JS ou pré-processadores CSS.

## Decisions

1. **HTML multi-arquivo com header/footer copiados por página** (sem partials/build).
   - Custo: atualizar header/footer exige editar N arquivos. Mitigação: documentado no AGENTS.md.
2. **Design tokens em `css/tokens.css`** (paleta "vidro sobre pedra", tipografia, espaçamento, raios, breakpoints) + `css/base.css` (reset/utilidades) + `css/estilo.css` (componentes e páginas).
3. **Paleta "vidro sobre pedra"**: fundo pedra `#f7f6f2`, marinho `#0f1f2c`, e gemas safira `#2f5f92`, esmeralda `#3f6f5a`, âmbar `#d99b2b`, âmbar profundo `#a06a18` (CTAs, AA) e rubi `#b3493a`. Tipografia Playfair Display (títulos) + Inter (corpo) via Google Fonts. Raio 8px; pílulas apenas em eyebrows.
4. **Conteúdo**: fonte da verdade em `docs/conteudo/novo/`; a Home em `docs/conteudo/homepage.md`. Dados institucionais preservados verbatim.
5. **Deploy**: branch `homologacao` servida pelo GitHub Pages; `main` só em deploy explícito.

## Risks / Trade-offs

- [Alterar header/footer em várias páginas] → Manter header/footer idênticos entre páginas e documentar no AGENTS.md; usar grep para localizar trechos.
- [Imagens de alta resolução aumentam o repo] → Otimizadas para ~60–330KB cada.
- [Múltiplas fontes de conteúdo] → `docs/conteudo/novo/` é a fonte da verdade; `spec-site.md` e `docs/conteudo/` ficam como legado.

## Migration Plan

1. Implementar páginas em `homologacao` (branch de trabalho).
2. Publicar via GitHub Pages e validar conteúdo e acessibilidade.
3. Deploy final apenas quando o usuário solicitar merge/deploy em `main`.

## Open Questions

- Nenhuma em aberto. Stack, escopo, arquitetura e design confirmados pelo usuário.
