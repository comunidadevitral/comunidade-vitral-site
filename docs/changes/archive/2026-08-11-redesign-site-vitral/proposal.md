## Why

O site atual da Comunidade Vitral rodava em Wix com design defasado e dependência da plataforma. Precisamos de um site estático moderno, de fácil manutenção via GitHub Pages, que apresente o conteúdo institucional da igreja com foco no visitante: alguém cansado que busca acolhimento ("venha como você está").

## What Changes

- Substitui o site Wix por site estático em HTML5 + CSS puro (sem build), com arquitetura de 7 páginas + 404: Home, Quem Somos, Jornada & Trilha de Novos, Encontros & PGs, Crianças & Família, Causas & Cidade e Contato.
- Conteúdo extraído e documentado em `docs/conteudo/novo/` (fonte da verdade; a Home em `docs/conteudo/homepage.md`), preservando verbatim os dados institucionais (telefone, e-mail, endereço, CNPJ, PIX, banco Itaú).
- Aplica o design system "Vitral Arquitetônico": paleta "vidro sobre pedra" em `css/tokens.css`, janela de vitral como assinatura, componentes retangulares (raio 8px), Playfair Display + Inter.
- Adiciona SEO por página (title, description, canônica, Open Graph, `twitter:card`, JSON-LD `Church`), `sitemap.xml`, `robots.txt`, `favicon.svg`, `og-image.png` (1200x630), `404.html` e acessibilidade WCAG 2.1 AA.
- Publica via GitHub Pages (subpath `/comunidadevitral/`, branch `homologacao`); `main` apenas em deploy explícito.

## Capabilities

### New Capabilities
- `site-estatico-vitral`: site estático multi-página com header/footer compartilhados, conteúdo preservado, SEO, acessibilidade e deploy no GitHub Pages.

### Modified Capabilities
<!-- Nenhuma; projeto novo. -->

## Impact

- Repo: `ismaelmmachado/comunidadevitral` (branch `homologacao` servida pelo GitHub Pages).
- Arquivos: 7 páginas HTML + 404 na raiz; `css/` (tokens, base, estilo); `js/menu.js`; `assets/` (img, logos, favicon, og-image, vitral).
- Documentação: `docs/conteudo/novo/` (fonte da verdade), `AGENTS.md`, `README.md`.
- Sem dependências novas de runtime (HTML/CSS/JS puro; Google Fonts).
