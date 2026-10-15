## Why

A comunidade precisa de um endereço digital para o Grande Banquete — experiência imersiva de 72 horas que funciona como catalisador da Jornada do Discípulo — hoje inexistente no site. Sem essa página, quem chega pelo site não descobre a experiência nem entende como participar (apadrinhamento), e a Vitral perde a chance de conectar visitantes ao coração do seu discipulado: a mesa.

## What Changes

- Nova página `grande-banquete.html` (8ª página do site) com 7 seções: hero, o que é (Lucas 14.15-24 + raízes históricas), conexão com a Jornada do Discípulo, as 72 horas, quem pode participar e apadrinhamento, vida depois do fim de semana e como participar/contato.
- Conteúdo-fonte da página em `docs/conteudo/novo/grande_banquete.md` (fonte da verdade).
- Menu de navegação atualizado em TODAS as páginas (7 existentes + 404): item "Grande Banquete" inserido após "Jornada".
- Bloco de divulgação na HOME (`index.html`) e bloco de convite na página Jornada (`jornada.html`) linkando a nova página.
- `sitemap.xml` atualizado com a 8ª URL.
- Ajustes de linguagem Vitral aplicados ao conteúdo fornecido: sem emojis, sem tom de "evento secreto"; "padrinho/apadrinhamento" como tradução acolhedora; "os 4 Times de Servidores (Mordomos)" conforme nomenclatura oficial.
- **BREAKING**: nenhum.

## Capabilities

### New Capabilities

(nenhuma)

### Modified Capabilities

- `site-estatico-vitral`: arquitetura passa de 7 para 8 páginas (+ `grande-banquete.html`); menu de navegação ganha 8 itens; sitemap.xml lista 8 URLs; nova exigência de conteúdo e integração da página Grande Banquete (hero, 72 horas, apadrinhamento, CTAs WhatsApp institucional e link para jornada.html).

## Impact

- Arquivos criados: `grande-banquete.html`, `docs/conteudo/novo/grande_banquete.md`, `.impeccable/surfaces/grande-banquete-html.md`, artefatos OpenSpec deste change.
- Arquivos modificados: nav nas 8 páginas HTML existentes (`index`, `quem-somos`, `jornada`, `encontros-e-pgs`, `criancas-e-familia`, `causas-e-cidade`, `contato`, `404`), blocos de divulgação em `index.html` e `jornada.html`, `sitemap.xml`.
- Sem mudanças de stack, dependências ou build. CSS reutiliza tokens/componentes existentes (Marca Nova); JS intocado.
- Publicação: GitHub Pages via branch homologacao (subpath `/comunidadevitral/`).
