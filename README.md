# Comunidade Vitral — Site

Novo site estático da **Comunidade Vitral** (Igreja Presbiteriana Independente Vitral),
em substituição ao site em Wix. Todo o site — HOME, subpáginas e 404 — usa a identidade
**"Marca Nova"** (verde petróleo/verde acinzentado e Montserrat), com o emblema oficial
da marca no hero e a tira de 4 cores no rodapé.

Versão atual: **v3.0.1** · Branch de trabalho: `homologacao`

Publicado em: <https://ismaelmmachado.github.io/comunidadevitral/>

## Páginas

| Página | Arquivo |
|---|---|
| HOME | `index.html` |
| Quem Somos | `quem-somos.html` |
| No Que Cremos | `no-que-cremos.html` |
| A Jornada & Trilha de Novos | `jornada.html` |
| O Grande Banquete | `grande-banquete.html` |
| Encontros & PGs | `encontros-e-pgs.html` |
| Crianças & Família | `criancas-e-familia.html` |
| Causas & Cidade | `causas-e-cidade.html` |
| Contato & Guia do Visitante | `contato.html` |
| 404 | `404.html` |

## Stack

- **HTML5 + CSS puro** — sem build step, zero dependências.
- Fonte única: Montserrat (400–800), via Google Fonts, em todas as páginas.
- Design tokens: `css/tokens.css` — paleta "Marca Nova" (petróleo/sálvia/cinzas).
- Emblema da marca no hero (`assets/logos/logo-vitral.png`) e tira de 4 cores no footer.
- JS mínimo: `js/menu.js`.

## Design

- **Marca Nova** (v3): identidade única em todo o site — verde petróleo `#005f6b` + verde acinzentado
  (sálvia) `#94a69a`/`#e9ede9`, quase-preto `#1f2421` e Montserrat. O emblema oficial entra no hero
  da HOME numa moldura clara; a tira de 4 cores (safira/esmeralda/âmbar/rubi) permanece no rodapé.
- Specs do sistema visual: `docs/specs/marca-nova.md`, `docs/specs/site-estatico-vitral.md`
- Specs OpenSpec: `docs/specs/site-estatico-vitral.md`, `docs/specs/marca-nova.md`
  (changes concluídos em `docs/changes/archive/`).

## Conteúdo

- Fonte da verdade das páginas: `docs/conteudo/novo/` (a Home está em `docs/conteudo/homepage.md`).
- Conteúdo antigo (10 páginas Wix) preservado em `docs/conteudo/` e `docs/raw/` para referência.
- Imagens: `assets/img/` (fotos) e `assets/logos/`.

## Rodar localmente

Abra `index.html` diretamente no navegador (site estático, sem servidor).

## Publicar

O GitHub Pages serve a raiz da branch `homologacao`. Basta fazer push nessa branch.
`main` só é usada em deploys explícitos.
