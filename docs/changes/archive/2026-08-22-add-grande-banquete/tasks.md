## 1. Conteúdo e documentação

- [x] 1.1 Criar `docs/conteudo/novo/grande_banquete.md` com o conteúdo aprovado (linguagem Vitral, sem emojis, terminologia normalizada)
- [x] 1.2 Criar brief de superfície `.impeccable/surfaces/grande-banquete-html.md` (modo Persuade, padrão dos briefs existentes)

## 2. Página nova

- [x] 2.1 Criar `grande-banquete.html`: head completo (title, description, canonical, OG/twitter, favicon, Montserrat, 3 CSS), skip-link, header com nav e `aria-current="page"`
- [x] 2.2 Implementar as 7 seções: hero (`.page-banner` + `cafe-encontros.jpg`), o que é (Lucas 14 + raízes em `.grid`/`.card`), conexão com a Vitral (3 itens), as 72 horas (`.feature-list` numerado), quem pode participar + apadrinhamento (lista + `.card-dark`), depois do fim de semana (3 cards), CTA final (`.section-dark`)
- [x] 2.3 Footer idêntico às demais páginas + `js/menu.js`

## 3. Integração

- [x] 3.1 Inserir item "Grande Banquete" no menu das 8 páginas HTML + 404 (após "Jornada")
- [x] 3.2 Adicionar bloco de divulgação na HOME (`index.html`) linkando a página
- [x] 3.3 Adicionar convite ao final da seção da Jornada (`jornada.html`) linkando a página
- [x] 3.4 Atualizar `sitemap.xml` com `grande-banquete.html`

## 4. Verificação e entrega

- [x] 4.1 Rodar detector impeccable (`node detect.mjs --json grande-banquete.html`) e corrigir apontamentos
- [x] 4.2 Validar links relativos internos, `aria-current`, og:image, contraste AA e responsividade 320px+
- [x] 4.3 `openspec validate --change add-grande-banquete`
- [x] 4.4 Atualizar checkboxes deste tasks.md conforme execução
