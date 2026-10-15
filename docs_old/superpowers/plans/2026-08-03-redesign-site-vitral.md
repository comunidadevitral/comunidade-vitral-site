# Redesign do Site Comunidade Vitral — Implementation Plan

> **Para workers agentic:** Execute task a task com checkpoints. Use checkboxes (`- [ ]`) para rastreio.

**Goal:** Substituir o site Wix da Comunidade Vitral por site estático (HTML/CSS puro), com conteúdo extraído por completo e novo design "Vitral contemporâneo", publicado no repo `ismaelmmachado/comunidadevitral` via GitHub Pages.

**Architecture:** Site estático multi-página, sem build, com tokens de design em CSS e header/footer compartilhados (copiados por página). Conteúdo extraído em `docs/conteudo/` como fonte da verdade. Especificação via openspec CLI e docs/superpowers.

**Tech Stack:** HTML5, CSS puro (design tokens), JS mínimo (menu mobile), Google Fonts (Playfair Display + Inter), GitHub Pages.

## Global Constraints

- Conteúdo preservado verbatim do site Wix (textos e dados institucionais).
- Idioma pt-BR.
- Mobile-first; acessibilidade AA (contraste ≥4.5:1, skip-link, `prefers-reduced-motion`).
- Caminhos relativos (subpath do Pages).
- Sem emojis em código/comentários; sem comentários desnecessários.
- Branch `homologacao` é a branch de trabalho; Pages serve `homologacao`.
- html lang="pt-BR".

---

### Task 1: Extração — baixar HTML bruto das 10 páginas

**Files:**
- Create: `docs/raw/<slug>.html` (10 arquivos)

- [ ] **Step 1:** Baixar HTML renderizado de cada página com `wget` para `docs/raw/` (index, sobre, mensagens, encontros, voluntariado, como-contribuir, visite-nos, templo, grande-banquete, link-bio).
- [ ] **Step 2:** Conferir que todos os arquivos têm >100KB e contêm o conteúdo esperado (grep por trecho-chave).
- [ ] **Step 3:** Commit.

### Task 2: Extração — markdown estruturado por página

**Files:**
- Create: `docs/conteudo/<slug>.md` (10 arquivos)

- [ ] **Step 1:** Converter cada HTML em markdown estruturado (títulos, parágrafos, listas, links, dados) preservando todo o conteúdo.
- [ ] **Step 2:** Revisar cada md: nenhum dado perdido (telefone, e-mail, PIX, banco, CNPJ, endereço, links ASAAS/WhatsApp/redes).
- [ ] **Step 3:** Commit.

### Task 3: Extração — baixar imagens para assets/

**Files:**
- Create: `assets/img/*` e `assets/logos/*`

- [ ] **Step 1:** Extrair todas as URLs `static.wixstatic.com` dos HTML.
- [ ] **Step 2:** Resolver cada URL para a imagem original (remover parâmetros `/v1/fill/...`, `/v1/crop/...` após `~mv2`/extensão).
- [ ] **Step 3:** Baixar para `assets/img/` (fotos) e `assets/logos/` (logos/ícones) com nomes descritivos.
- [ ] **Step 4:** Remover URLs duplicadas (mesma imagem em resoluções diferentes).
- [ ] **Step 5:** Commit.

### Task 4: Setup openspec CLI + convenções

**Files:**
- Create: `openspec/config.yaml`, `openspec/specs/redesign-site-vitral/spec.md`, `openspec/changes/...`
- Modify: `AGENTS.md`, `README.md`, `.gitignore`

- [ ] **Step 1:** Rodar `openspec init` na raiz (cria config.yaml, specs/, changes/).
- [ ] **Step 2:** Remover as notas soltas `openspec/001-004.md` (mover conteúdo essencial para docs/).
- [ ] **Step 3:** Criar change `redesign-site-vitral` com proposal.md, design.md, specs delta e tasks.md.
- [ ] **Step 4:** Reescrever `AGENTS.md` (stack HTML puro, branch homologacao, convenções, sem npm) e `README.md` (estado real).
- [ ] **Step 5:** Criar `.gitignore`.
- [ ] **Step 6:** Commit.

### Task 5: Design system — tokens.css

**Files:**
- Create: `css/tokens.css`

- [ ] **Step 1:** Definir variáveis: paleta vitral (degradê âmbar/terracota, azul-marinho, dourado, neutros), tipografia, espaçamento, raios, sombras, breakpoints.
- [ ] **Step 2:** Commit.

### Task 6: Design system — base.css e estilo.css

**Files:**
- Create: `css/base.css`, `css/estilo.css`
- Create: `js/menu.js`

- [ ] **Step 1:** `base.css`: reset, tipografia (Playfair Display + Inter via Google Fonts), utilidades, skip-link.
- [ ] **Step 2:** `estilo.css`: header sticky, nav (com dropdown "Mais"), hero com gradiente, cards, seções, botões pill, footer, mobile-first com menu hambúrguer.
- [ ] **Step 3:** `js/menu.js`: toggle do menu mobile + dropdown, respeitando `prefers-reduced-motion`.
- [ ] **Step 4:** Commit.

### Task 7: Construir HOME

**Files:**
- Create: `index.html`

- [ ] **Step 1:** Estrutura completa: head (SEO/OG/schema), header (logo + nav), hero "venha como você está", seções (menos programas/mais relacionamentos, crianças, contribuir), footer.
- [ ] **Step 2:** Validar HTML (tags fechadas), CSS carregado, links internos relativos.
- [ ] **Step 3:** Commit.

### Task 8: Construir SOBRE

**Files:**
- Create: `sobre.html`

- [ ] **Step 1:** Seções: hero, simples/missional/acolhedora, logotipo e significados, nossa história, parceiros.
- [ ] **Step 2:** Commit.

### Task 9: Construir MENSAGENS

**Files:**
- Create: `mensagens.html`

- [ ] **Step 1:** Seções: o que são mensagens, como ouvir (computador/tablet/celular), séries, versão A Mensagem (incluir a comparação do Pai Nosso), lista de mensagens (link SoundCloud/Spotify).
- [ ] **Step 2:** Commit.

### Task 10: Construir ENCONTROS

**Files:**
- Create: `encontros.html`

- [ ] **Step 1:** Seções: "proibida a entrada de pessoas perfeitas", o encontro em 5 perguntas (FAQ), café/música/informalidade, grupos pequenos.
- [ ] **Step 2:** Commit.

### Task 11: Construir VOLUNTARIADO

**Files:**
- Create: `voluntariado.html`

- [ ] **Step 1:** Seções: servir de 3 formas (na/a partir da/além da comunidade), grupos de trabalho.
- [ ] **Step 2:** Commit.

### Task 12: Construir COMO CONTRIBUIR

**Files:**
- Create: `como-contribuir.html`

- [ ] **Step 1:** Seções: princípios de contribuição (4 princípios), como contribuir (URNA, banco, PIX), dados (razão social, CNPJ).
- [ ] **Step 2:** Commit.

### Task 13: Construir VISITE-NOS

**Files:**
- Create: `visite-nos.html`

- [ ] **Step 1:** Seções: cultos de domingo (10:00–11:30), contato, endereço, mapa (link Google Maps), redes.
- [ ] **Step 2:** Commit.

### Task 14: Construir TEMPLO

**Files:**
- Create: `templo.html`

- [ ] **Step 1:** Seções: hero construção do templo, como contribuir (3 passos), cartões de contribuição ASAAS (mensal/bimestral/pontual).
- [ ] **Step 2:** Commit.

### Task 15: Construir GRANDE BANQUETE

**Files:**
- Create: `grande-banquete.html`

- [ ] **Step 1:** Seções: bem-vindo, história, propósito, como funciona, quem pode participar, o que acontece depois, contato WhatsApp.
- [ ] **Step 2:** Commit.

### Task 16: Construir LINK-BIO e 404

**Files:**
- Create: `link-bio.html`, `404.html`

- [ ] **Step 1:** `link-bio.html`: agregador de links (redes, Spotify, maps, WhatsApp channel, quem somos, onde estamos).
- [ ] **Step 2:** `404.html`: página amigável com link para a home.
- [ ] **Step 3:** Commit.

### Task 17: SEO + assets de identidade

**Files:**
- Create: `sitemap.xml`, `robots.txt`, `assets/favicon.svg`, `assets/og-image.svg`

- [ ] **Step 1:** `sitemap.xml` com as 10 URLs canônicas (base `https://ismaelmmachado.github.io/comunidadevitral/`).
- [ ] **Step 2:** `robots.txt` permitindo tudo + apontando sitemap.
- [ ] **Step 3:** `favicon.svg` (símbolo vitral) e `og-image.svg`.
- [ ] **Step 4:** Referenciar favicon e OG em todas as páginas.
- [ ] **Step 5:** Commit.

### Task 18: Verificação final

**Files:**
- Todos

- [ ] **Step 1:** Checar links internos quebrados (grep por href e conferir arquivos existentes).
- [ ] **Step 2:** Checar que todas as imagens referenciadas existem em `assets/`.
- [ ] **Step 3:** Conferir contraste/títulos por página (revisão visual estrutural).
- [ ] **Step 4:** Remover arquivos órfãos da sessão anterior (styles.css da raiz, src/, content/ se substituído).
- [ ] **Step 5:** Commit.

### Task 19: Publicar em homologacao e verificar Pages

**Files:**
- Todos

- [ ] **Step 1:** Push de `homologacao`.
- [ ] **Step 2:** Verificar `gh api repos/ismaelmmachado/comunidadevitral/pages` → `status: built` e conferir a URL pública.
- [ ] **Step 3:** Confirmar conteúdo na URL publicada.
