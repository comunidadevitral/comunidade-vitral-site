## Why

A auditoria de design contra as boas práticas de UX/UI mobile-first identificou lacunas técnicas com impacto direto no público do site (pessoas em São José do Rio Preto, majoritariamente mobile, muitas em redes 3G/4G): imagens sem formato next-gen (2,9 MB em JPG/PNG), zero `loading="lazy"` e zero dimensões explícitas (CLS), menu mobile funcional mas abaixo do padrão de conforto de toque, ausência de microinteração de press e um token de gradiente morto no design system. O bloco prático "onde e quando" — a informação mais buscada por visitantes de igreja — existe disperso (hero + contato) e merece destaque acionável na HOME.

## What Changes

- **Performance de mídia**: 15 imagens (`assets/img/*.jpg` + `decolores-placa.png`) convertidas para WebP q80 mantendo dimensões; referências `src` trocadas nos HTMLs; originais preservados no repositório como master; `loading="lazy"` nas imagens abaixo da dobra; `width`/`height` explícitos para eliminar CLS.
- **Bloco "Onde e Quando" na HOME**: card prático na seção "A mesa está posta…" com horário (domingos às 10h), endereço e botões "Traçar rota no Google Maps" e "Abrir no Waze" (nova aba, `rel="noopener"`).
- **Menu mobile**: dropdown atual vira drawer fullscreen (≤760px) com links ≥48px de altura, fechamento por Esc/clique-fora/link, trava de rolagem e foco devolvido ao botão Menu. Desktop (>760px) intocado.
- **Microinterações**: estados `:active` (press) em `.btn`, cards e links de navegação, respeitando `prefers-reduced-motion`.
- **Limpeza**: remoção do token morto `--grad-marca` de `css/tokens.css`.
- Rejeitados nesta mudança (com motivo registrado): modo escuro automático (`prefers-color-scheme`) — PRODUCT.md registra decisão de produto por modo claro único; rewrite do hero ("Igreja em Pessoas") — copy atual é escolha deliberada de acolhimento; logo horizontal oficial — asset inexistente no repositório.

## Capabilities

### New Capabilities

(nenhuma)

### Modified Capabilities

- `site-estatico-vitral`: requisito de navegação passa a exigir drawer fullscreen mobile com alvos ≥48px; novo requisito de performance de mídia (WebP, lazy loading, dimensões explícitas); novo cenário do bloco de rotas Maps/Waze na HOME.

## Impact

- Arquivos modificados: `index.html`, demais páginas com `<img>` (banner/hero/conteúdo), `css/tokens.css`, `css/base.css`, `css/estilo.css`, `js/menu.js`.
- Arquivos criados: `assets/img/*.webp` (15 conversões) + artefatos OpenSpec deste change.
- Nenhuma dependência nova de runtime; WebP via ferramenta local (PIL) no fluxo de trabalho, não no site.
- Risco controlado: navegadores sem WebP (<3% do mercado) não exibiriam fotos — mitigado pela decisão de substituição direta aceita pelo produto (suporte >97%, Safari 14+).
