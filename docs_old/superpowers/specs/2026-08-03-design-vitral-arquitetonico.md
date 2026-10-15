# Comunidade Vitral — Redesign v2 "Vitral Arquitetônico" (Spec de Design)

Data: 2026-08-03
Status: Aprovado (Direção A · Playfair · Paleta ok)

## Objetivo

Evoluir o design do site da Comunidade Vitral (v1 "Vitral contemporâneo") para **"Vitral Arquitetônico"** na **Direção A (Vitral Luminoso)**, mantendo a identidade "vitral" e o conteúdo das 10 páginas, com tipografia Playfair Display e a paleta "vidro sobre pedra".

## Decisões aprovadas

| Decisão | Escolha |
|---|---|
| Direção | **A · Vitral Luminoso** — hero editorial claro com janela de vitral em destaque |
| Tipografia dos títulos | **Playfair Display** (corpo segue em Inter) |
| Paleta | "Vidro sobre Pedra" aprovada |

## Conceito

O vitral é uma **janela por onde a luz entra**. O site é tratado como espaço arquitetônico: fundo pedra limpo e ordenado, com o vitral aparecendo como **painel-janela de facetas** (SVG) em pontos estratégicos (hero, divisores, footer). O degradê deixa de dominar os fundos e vira **faceta** em elementos pequenos.

## Paleta (tokens) — "Vidro sobre Pedra"

| Token | Cor | Uso |
|---|---|---|
| `--pedra` (fundo) | `#f7f6f2` | base do site |
| `--surface` | `#ffffff` | cards |
| `--ink` (texto) | `#1d262e` | títulos/texto |
| `--muted` | `#5d6a75` | corpo, metadados |
| `--border` | `#e5e1d7` | bordas/linhas |
| `--navy` | `#0f1f2c` | footer, seções escuras |
| `--navy-soft` | `#16324e` | gradiente marinho |
| `--safira` | `#2f5f92` | vidro (acento azul) |
| `--esmeralda` | `#3f6f5a` | vidro (acento verde) |
| `--ambar` | `#d99b2b` | vidro / CTA |
| `--rubi` | `#b3493a` | vidro (acento quente) |
| `--grad-vitral` | âmbar→rubi | facetas e botão primário (elementos pequenos) |
| `--grad-navy` | marinho | banner/footer |

## Tipografia

- Títulos: **Playfair Display** (serif), escala grande, editorial.
- Corpo: **Inter**.
- Labels: `uppercase`, tracking `0.14em`–`0.16em`.

## Componentes e layout (Direção A)

- **Header:** claro (blur), logo + nav, dropdown "Mais".
- **Hero (HOME):** editorial claro assimétrico — eyebrow (safira), H1 grande (Playfair, grafite), subtítulo (muted), CTAs (primário gradiente âmbar→rubi + outline grafite), e **janela de vitral (SVG de facetas)** à direita.
- **Banner de subpáginas:** marinho com foto (mantém o padrão atual).
- **Cards:** painéis retangulares (raio 8px), borda fina, elevação sutil; card-destaque com gradiente vitral.
- **Botões:** retangulares (raio 8px), primário = faceta (âmbar→rubi), secundário = outline, navy, gold (âmbar).
- **Janela de vitral (`assets/vitral.svg`):** arco de vidro com facetas em safira/esmeralda/âmbar/rubi e filetes claros — assinatura do site (hero, footer via CSS).
- **Footer:** marinho com tira de vitral (via CSS `::before`), contato/redes.
- **Seções:** fundo pedra com linhas divisórias finas; poucas seções escuras (marinho).

## Escopo de mudança

- `css/tokens.css`, `css/base.css`, `css/estilo.css` — nova paleta, hero editorial, cards/botões retangulares, janela de vitral.
- `assets/vitral.svg` (novo), `assets/favicon.svg` e `assets/og-image.svg` (paleta nova).
- HTML: `index.html` (hero Direção A) e `templo.html` (hero → banner marinho).
- Conteúdo e estrutura das demais páginas permanecem.

## Fora de escopo

- Alteração de conteúdo/textos.
- Mudança de navegação ou URLs.
- As demais decisões (Direção B, Fraunces) descartadas nesta versão.
