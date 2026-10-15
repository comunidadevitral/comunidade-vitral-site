## Context

Site estático sem build step; otimizações de mídia acontecem no fluxo de trabalho (PIL local), não em runtime. Header já é sticky com backdrop-filter (estilo.css:4-11); grids colapsam @760px; menu mobile atual é dropdown absoluto (`js/menu.js` alterna `.open`, fecha por clique-fora nos dropdowns). 15 imagens somam ~2,9 MB (14 JPG + 1 PNG quantizado). Zero `loading="lazy"`, zero `width`/`height` — CLS latente. Token `--grad-marca` definido em tokens.css e nunca referenciado. Ver proposal.md para motivação.

## Goals / Non-Goals

**Goals:**
- Página inicial e subpáginas carregando imagens WebP (<2 MB no conjunto) sem salto de layout.
- Visitante mobile chega ao "onde e quando" com rota acionável em um toque.
- Menu mobile confortável para polegar (48px) com fechamento previsível.
- Feedback tátil de press coerente com o sistema Marca Nova.

**Non-Goals:**
- Modo escuro (decisão de produto: apenas claro).
- Mudança de copy do hero ou do posicionamento visual das páginas.
- Pipeline de build/CI para imagens; conversão permanece manual no fluxo.
- Suporte a navegadores sem WebP (decisão aceita: substituição direta, >97% de suporte).

## Decisions

1. **WebP q80 por substituição direta de `src`** (sem `<picture>`): HTML enxuto, suporte >97%; originais JPG/PNG permanecem no repo como master para re-encodeções futuras. Alternativa descartada: `<picture>` com fallback — verbosidade sem ganho prático para o público-alvo.
2. **Lazy + dimensões explícitas**: `loading="lazy"` em toda imagem fora da primeira dobra; banners/hero eager. `width`/`height` extraídos dos arquivos reais via script, garantindo aspect-ratio nativo do navegador (CLS zero) sem CSS adicional.
3. **Drawer fullscreen**: overlay `position: fixed` cobrindo o viewport, fundo branco, links empilhados ≥48px, `Esc`/clique-fora/link fecham, `overflow` travado no `body` enquanto aberto, foco devolvido ao `.nav-toggle`. Mantém os mesmos ids/classes base (`#nav-menu`, `.open`) para minimizar mudanças em 9 arquivos HTML — só CSS e JS mudam.
4. **Rotas Maps + Waze**: deep links estáveis — Maps `https://www.google.com/maps/search/?api=1&query=<endereço+codificado>` (formato já usado no hero-meta) e Waze `https://waze.com/ul?q=<endereço+codificado>&navigate=yes`. Ambos nova aba + `rel="noopener"` (padrão institucional).
5. **Press states**: `transform: scale(0.98)` em `.btn:active`, cards e links do nav; sem transição longa, respeitado por quem usa `prefers-reduced-motion` (transform mínimo e instantâneo não configura motion problemático).
6. **Remoção de `--grad-marca`**: token morto; o mundo sóbrio da Marca Nova usa `--grad-banner`. Remoção mantém o design system honesto.

## Risks / Trade-offs

- [Navegadores pré-2020 sem WebP] → aceito pelo produto (<3% do mercado); master preservado permite reintroduzir `<picture>` se necessário.
- [Drawer muda comportamento conhecido de usuários atuais] → padrão consolidado na web; benefício de toque supera estranheza transitória.
- [Waze web deep link pode abrir app ou site conforme dispositivo] → comportamento esperado do `ul?q=`; rota correta em ambos.
- [15 conversões manuais podem divergir do master futuro] → registrado no tasks.md que novas fotos devem nascer em WebP a partir do master.

## Migration Plan

Commit único na `homologacao`; Pages reconstrói. Rollback = revert (originais intactos no repo).

## Open Questions

Nenhuma.
