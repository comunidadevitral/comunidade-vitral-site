# Comunidade Vitral — Redesign do Site (Spec de Design)

Data: 2026-08-03
Status: Aprovado

## Objetivo

Substituir o site em Wix da Comunidade Vitral por um site estático moderno, preservando **todo** o conteúdo (textos, dados institucionais, links e imagens) e aplicando um novo design na direção **Vitral contemporâneo**.

## Contexto

- Fonte de conteúdo: https://www.comunidadevitral.com.br (site Wix/Thunderbolt)
- Repo de destino: `ismaelmmachado/comunidadevitral` (público, GitHub Pages ativo em `homologacao`)
- Sessão anterior deixou extração parcial (6 páginas como texto bruto), um design-system "Stripe" rosa que **será substituído**, notas markdown soltas em `openspec/` e apenas um protótipo da home.
- Stack dos projetos do usuário (trilhas, trilha_de_novos): HTML5 + CSS puro, sem build, GitHub Pages.

## Inventário de páginas (extração)

10 páginas estáticas confirmadas (menu principal + subpáginas):

| # | Slug | Título | Observação |
|---|---|---|---|
| 1 | `/` (index) | HOME | hero "venha como você está", missão, crianças, contribuir |
| 2 | `/sobre` | SOBRE | simples/missional/acolhedora, logotipo, história, parceiros |
| 3 | `/mensagens` | MENSAGENS | ouvir mensagens, séries, versão A Mensagem, podcast |
| 4 | `/encontros` | ENCONTROS | o encontro, 5 perguntas, grupos pequenos |
| 5 | `/voluntariado` | VOLUNTARIADO | 3 formas de servir, grupos de trabalho |
| 6 | `/como-contribuir` | COMO CONTRIBUIR | princípios, urna/PIX/banco, CNPJ |
| 7 | `/visite-nos` | VISITE-NOS | endereço, horários, contato |
| 8 | `/templo` | TEMPLO | construção do templo, contribuição ASAAS |
| 9 | `/grande-banquete` | GRANDE BANQUETE | experiência de 72h, contato WhatsApp |
| 10 | `/link-bio` | LINK-BIO | agregador de links (redes, Spotify, maps, WhatsApp) |

Fora de escopo: "Página de Eventos" e "Calendário" (app Wix sem URL estática acessível).

## Dados institucionais a preservar (verbatim)

- Nome: Comunidade Vitral / Igreja Presbiteriana Independente Vitral (IPI)
- Tagline: "igreja em pessoas" / "Uma comunidade simples, missional e acolhedora"
- Telefone: 17 99619-5302 (`tel:+5517996195302`)
- E-mail: contato@comunidadevitral.com.br
- Endereço: Avenida Sebastião Tavares da Silva, 1191 - Jardim Vista Alegre, São José do Rio Preto - SP - CEP 15061660
- Redes: Instagram (instagram.com/comunidadevitral), YouTube (youtube.com/c/ComunidadeVitral), Facebook (facebook.com/comunidadevitral), Spotify (show 1prjsrcxPho9otrP1VUWT4), Canal WhatsApp (0029VaDcpgg9sBI4RrOepp1C)
- Contribuição: URNA, Itaú Ag 8299 C/C 24420-5, PIX financeiro@comunidadevitral.com.br
- Razão social: Presbitério Rio Preto da IPIB — CNPJ 49.075.286/0001-63
- Templo (ASAAS): mensal c/3m32r7l2p3la45jh, bimestral c/eyw4qqd2859mawza, pontual c/p3roqnn1bx733dlq
- Grande Banquete: WhatsApp 17981010555 (Cláudia Torquato)

## Direção de design — Vitral contemporâneo

Conceito: blocos de cor com degradê inspirados no vitral (vidros coloridos que deixam a luz do amor passar). Tom acolhedor, simples, contemporâneo, sem exagero.

### Paleta (tokens)
- Degradê principal (ânima): âmbar → terracota → rosa-queimado (hero e acentos)
- Azul-marinho profundo (texto, fundos escuros)
- Dourado (destaques/CTA)
- Neutros quentes: fundo claro creme, superfície branca, bordas suaves
- Texto: azul-marinho sobre fundo claro; branco sobre blocos escuros

### Tipografia
- Títulos: Playfair Display (Google Fonts)
- Corpo: Inter (Google Fonts)
- Escala fluida com clamp

### Componentes
- Header: sticky, logo + nav (dropdown "Mais"), menu mobile
- Hero: gradiente + foto, título, subtítulo, CTAs
- Cards: superfície branca, borda, raio generoso, hover com elevação
- Seções alternadas claro/escuro
- Botões: pill (raio 999px), primário dourado/gradiente, secundário outline
- Footer: logo IPI, contato, endereço, redes, copyright

## Requisitos transversais

- Mobile-first, acessibilidade AA (skip-link, contraste 4.5:1, `prefers-reduced-motion`, foco visível)
- SEO: title/description por página, canônica, Open Graph, schema.org `Church` + `LocalBusiness` no JSON-LD
- `sitemap.xml`, `robots.txt`, `favicon.svg`, `og-image.svg`, `404.html`
- Imagens: hospedadas localmente em `assets/`; alt + lazy-loading
- Caminhos relativos (subpath do Pages: `https://ismaelmmachado.github.io/comunidadevitral/`)

## Estrutura-alvo

```
index.html, sobre.html, mensagens.html, encontros.html, voluntariado.html,
como-contribuir.html, visite-nos.html, templo.html, grande-banquete.html,
link-bio.html, 404.html
css/ tokens.css | base.css | estilo.css
js/  menu.js
assets/ img/ (fotos) | logos/ | favicon.svg | og-image.svg
docs/ raw/ (HTML baixado) | conteudo/ (markdown estruturado) | inventario.md
openspec/ (formato CLI: config.yaml, specs/, changes/)
AGENTS.md, README.md, .gitignore, sitemap.xml, robots.txt, .nojekyll
```

## Deploy

- Branch `homologacao` servida pelo GitHub Pages (regra única, alinhada aos projetos existentes)
- `main` reservada para deploys explícitos
- Verificação via `gh api repos/ismaelmmachado/comunidadevitral/pages` → `status: built`

## Fora de escopo

- Backend/CMS, login, integrações novas
- Migração do app de eventos/calendário do Wix
- Páginas de eventos dinâmicas
