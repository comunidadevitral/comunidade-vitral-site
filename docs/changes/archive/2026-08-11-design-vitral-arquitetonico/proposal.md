## Why

O site (v1.0.0) usa o design "Vitral contemporâneo" com degradê dominante e cards/ botões muito arredondados, sem caráter editorial. Para uma igreja reformada presbiteriana (simplicidade, reverência, acolhimento, foco na Palavra), aprovamos o redesign **"Vitral Arquitetônico"** na Direção A: o vitral como janela de luz, fundo limpo, ordem e acolhimento.

## What Changes

- Nova paleta "vidro sobre pedra": fundo pedra `#f7f6f2`, grafite `#1d262e`, marinho `#0f1f2c` e cores de vidro safira `#2f5f92`, esmeralda `#3f6f5a`, âmbar `#d99b2b`, âmbar profundo `#a06a18` (CTAs, AA) e rubi `#b3493a`.
- Degradê deixa de dominar os fundos e vira **faceta** (botão primário, card destaque, cabeçalho de tabela) e é escurecido (âmbar profundo→rubi) para contraste AA com texto branco.
- Hero da HOME editorial claro e assimétrico, com **janela de vitral (SVG de facetas)**.
- Cards e botões passam de arredondados (raio 18px / pill) para **retangulares arquitetônicos** (raio 8px).
- Novos assets: `assets/vitral.svg`, atualização de `favicon.svg` e `og-image.png` (1200x630).
- Tipografia dos títulos permanece **Playfair Display** (corpo Inter).
- Subpáginas com banner marinho (padrão das subpáginas).

## Capabilities

### New Capabilities
- `design-vitral-arquitetonico`: sistema visual "Vitral Arquitetônico" aplicado ao site estático (paleta vidro sobre pedra, janela de vitral, componentes retangulares editoriais).

### Modified Capabilities
<!-- Nenhuma; mudança visual sem alteração de conteúdo/navegação. -->

## Impact

- `css/tokens.css`, `css/base.css`, `css/estilo.css` — nova paleta e componentes.
- `assets/vitral.svg` (novo), `assets/favicon.svg`, `assets/og-image.svg`.
- `index.html` (hero Direção A) e subpáginas (banner marinho).
- Conteúdo, navegação e URLs permanecem iguais.
