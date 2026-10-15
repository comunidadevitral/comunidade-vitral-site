# AGENTS.md — Comunidade Vitral

Guia de convenções e contexto para agentes que trabalham neste repositório.

## Regra de Ouro (nunca esquecer)

1. **Idioma: interagir SEMPRE em português (pt-BR)** com o usuário — em qualquer conversa, resposta ou resumo, neste e em qualquer repositório.
2. **"Salva"** → commit e push na branch `homologacao` (branch de trabalho padrão).
3. **"Salva em main"** (explícito) → `main`.
4. `main` só é usado quando solicitado explicitamente (deploy).

## Projeto

Novo site estático da Comunidade Vitral (IPIB São José do Rio Preto), em substituição ao site Wix.
Publicado via GitHub Pages: `https://ismaelmmachado.github.io/comunidadevitral/`

### Stack
- **HTML5 + CSS puro** — sem build step, zero dependências de runtime.
- Identidade única "Marca Nova" em todo o site: verde petróleo + verde acinzentado (sálvia), tipografia **Montserrat**, via Google Fonts.
- Design tokens: `css/tokens.css` — paleta Marca Nova padrão; especificação completa em `docs/specs/marca-nova.md`.
- JS mínimo: `js/menu.js` (menu mobile).
- O hero da HOME usa o emblema da marca (`assets/logos/logo-vitral.png`); a tira de 4 cores é marca inegociável.

### Estrutura
- 9 páginas estáticas de conteúdo na raiz: `index`, `quem-somos`, `no-que-cremos`, `jornada`, `encontros-e-pgs`,
  `grande-banquete`, `criancas-e-familia`, `causas-e-cidade`, `contato` + `404.html`.
- `css/` (tokens, base, estilo), `js/`, `assets/` (img, logos, favicon, og-image).
- `docs/` — conteúdo extraído (`conteudo/`, `conteudo/novo/`, `raw/`), legado (`openspec-legado/`) e propostas (`propostas/`).
- `docs/specs/` — documentação spec-driven (specs: `site-estatico-vitral`, `marca-nova`; `config.yaml`); changes concluídos em `docs/changes/archive/`.
- `AGENTS.md`, `README.md` — documentação do projeto.

### Conteúdo
- Conteúdo das 9 páginas em `docs/conteudo/novo/*.md` (fonte da verdade); a Home está
  em `docs/conteudo/homepage.md`.
- Material da formação: apostilas da Trilha de Novos vivem no repo
  `ismaelmmachado/trilha_de_novos` (docs/apostilas/); análise de congruência
  apostila × site em `docs/propostas/congruencia-apostila-v2.2-site.md`.
- Preservar verbatim: textos, telefone 17 99619-5302, e-mail contato@comunidadevitral.com.br,
  endereço, CNPJ 49.075.286/0001-63, PIX financeiro@comunidadevitral.com.br, banco Itaú Ag 8299.
- Botões de WhatsApp usam o número institucional `https://wa.me/5517996195302`.
- Header e footer são repetidos em cada página HTML — ao alterar, atualizar **todas** as páginas.

## Deploy (GitHub Pages)

- GitHub Pages serve a raiz (`/`) da branch **`homologacao`**.
- Sem build step: `git push origin homologacao` publica o conteúdo commitado.
- Verificação: `gh api repos/ismaelmmachado/comunidadevitral/pages` → `status: built`.

## Convenções

- Idioma: português (pt-BR).
- Sem emojis em código/comentários; sem comentários no código salvo se solicitado.
- Mobile-first; acessibilidade AA; caminhos relativos (subpath do Pages).

## Design

O sistema visual "Marca Nova" é especificado em `docs/specs/marca-nova.md` e implementado
nos tokens de `css/tokens.css`. Estado: **todo o site** (HOME, subpáginas e 404) usa a Marca Nova
como padrão único — um só mundo visual.

## Agent skills

### Issue tracker

Local markdown issue tracker (files under `.scratch/`). See `docs/agents/issue-tracker.md`.

### Triage labels

Default triage labels (`needs-triage`, `needs-info`, `ready-for-agent`, `ready-for-human`, `wontfix`). See `docs/agents/triage-labels.md`.

### Domain docs

Single-context layout (one `GLOSSARY.md` + `docs/adr/` at repo root). See `docs/agents/domain.md`.
